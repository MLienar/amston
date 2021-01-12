<template>
    <div class="content-box">
        <splashText />
    </div>
</template>

<script>

import splashText from '../home/splashText'

export default {
    name: 'contentBox',
    components: {
        splashText
        }
}
</script>

<style lang="scss">
    .content-box {
        padding: 15vh 0 5vh 15vh;
        display: flex; 
        flex-flow: row nowrap;
        overflow-x: hidden;
    }
</style>