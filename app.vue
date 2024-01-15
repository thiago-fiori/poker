<template>
  <div class="sala">
    <Mesa>
      <Assento
        v-for="(Jogador, index) in jogadores"
        :key="index"
        :style="positionParaStyle(playerPosition(700, 400, index, 8))"
      ></Assento>
    </Mesa>

    <footer>
      <button @click="adicionarJogador">Adicionar Jogador</button>
      <button @click="removerJogador">Remover Jogador</button>
    </footer>
  </div>
</template>

<script setup>
function positionParaStyle(position) {
  console.log(position);
  const style = {
    position: "relative",
    left: `${position.x}px`,
    top: `${position.y}px`,
    " background-color": "blue",
  };
  console.log(style);
  return style;
}

function playerPosition(W, H, index, maxPlayers) {
  // Semi-eixos da elipse
  let a = W / 2;
  let b = H / 2;

  // Calcular o ângulo para o jogador atual
  let angle = 2 * Math.PI * (index / maxPlayers);

  // Calcular posição x e y
  let x = Math.round(a * Math.cos(angle));
  let y = Math.round(b * Math.sin(angle));

  return { x: x, y: y };
}

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
body {
  padding: 0;
}

footer {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

button {
}

.sala {
  height: 90vh;
  background-color: brown;
  margin: 0;
  position: relative;
}
</style>
