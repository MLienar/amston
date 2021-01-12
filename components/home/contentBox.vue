<template>
    <div class="content-box">
        <splashText />
        <songSlider />
    </div>
</template>

<script>

import splashText from '../home/splashText'
import songSlider from '../home/songSlider'

export default {
    name: 'contentBox',
    components: {
        splashText,
        songSlider,
        }
}
</script>

<style lang="scss">
    .content-box {
        padding: 15vh 0 7vh 15vh;
        display: flex; 
        flex-flow: row nowrap;
        overflow-x: hidden;
    }
</style>