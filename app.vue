<template>
  <div class="sala">
    <Mesa>
      <Campo>
        <Baralho></Baralho>
        <Carta v-for="carta in cartasNaMesa"></Carta>
      </Campo>
      
      <Assento
        v-for="(_, idx) in Array(jogadores)"
        :key="idx"
        :style="indexToStyle(1200, 600, idx, 100, 8)"
      ></Assento>
    </Mesa>

    <footer>
      <button @click="adicionarJogador">Adicionar Jogador</button>
      <button @click="removerJogador">Remover Jogador</button>
    </footer>
  </div>
</template>

<script lang="ts" setup>

const cartasNaMesa = useState("cartasNaMesa", ()=>[]);
const turno = useState("turno", ()=>"preFlop")
const mapaDeTurnos = {
  preFlop: {cartas: 0, proximo: "flop"},
  flop: {cartas: 3, proximo: "turn"},
  turn: {cartas: 1, proximo: "river"},
  river: {cartas: 1, proximo: null},
}

const baralho = [];
const naipes = ['♥', '♦', '♣', '♠'];
const valores = ['A', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K'];

for (const naipe of naipes) {
    for (const valor of valores) {
        baralho.push(`${valor}${naipe}`);
    }
}

console.log(baralho);

const indexToStyle = (
  width: number,
  height: number,
  index: number,

  actorSize = 200,
  players = 8
) => {
  const phase = Math.PI / 8;
  const theta = ((2 * Math.PI) / players) * index + phase;
  const rx = width / 2 + actorSize / 2; // Raio horizontal da elipse
  const ry = height / 2 + actorSize / 2; // Raio vertical da elipse
  const x = rx + rx * Math.cos(theta) - actorSize;
  const y = ry + ry * Math.sin(theta) - actorSize;
  return {
    position: "absolute",
    left: `${x}px`,
    top: `${y}px`,
  };
};

const jogadores = useState("jogadores", () => 1);
const adicionarJogador = function () {
  console.log("Botão apertado");
  jogadores.value++;
  //console.log(jogadores);
};

const removerJogador = function () {
  console.log("Botão apertado");

  if (jogadores.value > 0) {
    jogadores.value--;
  }
  //console.log(jogadores);
};
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  padding: 0;
  margin: 0;
}

footer {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 2rem;
  gap: 1rem;
}

.sala {
  height: 100dvh;
  background-color: orange;
  margin: 0;
  position: relative;
  display: flex;
  flex-direction: column;
}

button {
  padding: 1rem;
  border-radius: 0.5rem;
  border: none;
  background-color: #333;
  color: white;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  background-color: #555;
}
</style>
