<template>
    <div class="content-box">
        <div class="overlay"></div>
        <splashText />
        <songSlider/>
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
        },
}

</script>

<style lang="scss">
    .content-box {
        padding: 15vh 0 7vh 15vh;
        display: flex; 
        flex-flow: row nowrap;
        overflow-x: hidden;
        justify-content: space-between;
        width: 92vw;
        position: relative;
        .overlay {
            width: 100%;
            height: 100%;
            background: #000000;
            opacity: 0;
            display: none;
            position: absolute;
            right: 0;
            bottom: 0;
        }
    }
</style>