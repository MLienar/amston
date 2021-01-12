<template>
    <div class="splash-text">
        <div class="hero-text">
            <h1><span class="bodoni-text" id="hiphop">Hip-Hop</span>
            <span class="poor-text" id="artist">Artist</span>
            <span class="bodoni-text" id="and">&</span>
            <span class="poor-text" id="beatmaker">Beatmaker</span></h1>
        </div>
        <div class="adress">
            <h2><span class="bodoni-text">from</span>
            <span class="poor-text">paris</span></h2>
        </div>
    </div>  
</template>

<script>
export default {
    name: 'splashText'
}
</script>

<style lang="scss">
    .splash-text {
        text-transform: uppercase;
        display: flex;
        flex-flow: column nowrap;
        justify-content: space-between;
        margin-top: 5vh;
        h1 {
            font-size: 3em;
            display: flex;
            flex-flow: column nowrap;
            font-weight: 400;
            }
            #artist {
                margin-left: 5vw;
            }
            #and {
                margin-left: 14vw;
            }
            #beatmaker {
                margin-left: 10vw;
            }
        }
        h2 {
            font-weight: 400;
            display: flex;
            flex-flow: column nowrap;
            .bodoni-text {
                font-size: 0.7em;
            }
            .poor-text {
                font-size: 2em;
            }
        }
    .bodoni-text {
        font-family: 'Bodoni Moda', sans-serif;
        
    }
    .poor-text {
        font-family: 'Poor Story', sans-serif;
    }
</style>