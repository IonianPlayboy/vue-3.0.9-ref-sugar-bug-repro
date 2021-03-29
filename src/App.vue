<template>
    {{ msg }}
    {{ splittedMsg() }}
    {{ getNumberInMsg() }}
</template>

<script lang="ts"></script>
<script lang="ts" setup>
ref: msg = "Hello World 42 !";

// This works fine
const splittedMsg = () => msg.split(" ");

// This does not
const getNumberInMsg = () => {
    if (!msg) return null;
    const [currMatch] = msg.match(/\d+/) ?? [];
    if (!currMatch) return null;
    return Number(currMatch);
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
