<template>
    <div class ="baralho" @click="console.log('Baralho clicado')">

    </div>
</template>

<style scoped>
.baralho{
    background-color: white;
    height: 120px;
    width: 72px;
    border-radius: 5px;
    cursor: pointer;
}

.baralho:hover{
    box-shadow: 1px 1px rgb(0, 0, 0, 0.5);
}
</style>