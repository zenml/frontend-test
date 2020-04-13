<template>
    <div id="app">
        <TransList />
    </div>
</template>

<script>
import TransList from "./components/TransList.vue";

export default {
    name: "App",
    components: {
        TransList
    }
};
</script>

<style lang="less">
#app {
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
