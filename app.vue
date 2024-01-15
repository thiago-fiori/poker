<template>
  <div class="sala">
    <Mesa>
      <Assento v-for="Jogador in Array(jogadores)"></Assento>
    </Mesa>

    <footer>
      <button @click="adicionarJogador">Adicionar Jogador</button>
      <button @click="removerJogador">Remover Jogador</button>
    </footer>

  </div>
</template>

<script setup>
  const jogadores = useState("jogadores", () =>1);
  const adicionarJogador = function(){
    console.log("Botão apertado");
    jogadores.value++;
    //console.log(jogadores);
  }

  const removerJogador = function(){
    console.log("Botão apertado");
    
    if(jogadores.value > 0){
      jogadores.value--;
    }
    //console.log(jogadores);
  }
</script>

<style scoped>
  body{
    padding: 0;
  }

  footer{
    display: flex;
    flex-direction: row;
    justify-content: center;
  }

  button{
  
  }

  .sala{
    height: 90vh;
    background-color: brown;
    margin: 0;
  }
</style>