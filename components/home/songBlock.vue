<template>
    <div class="song-block">
        <div class="album-cover">
            <div class="album-overlay"></div>
            <div class="play-button" @click="playSound">
                <img src="~assets/play.svg" alt="play-button">
            </div>
            <img src="~assets/papillon.jpg" alt="couverture">
        </div>
        <div class="album-title">
            <h2>- Peinture Fraîche -</h2>
        </div>
    </div>
</template>

<script>
const {Howl, Howler} = require('howler');

export default {
    name: 'songBlock',
    data() {
        return {
            song: "http://matheolienard.fr/aura.mp3"
        }
    },
    methods: {
        playSound() {
            var sound = new Audio(this.song);
            sound.play();
        }
    },
}
</script>

<style lang="scss">
    .song-block{
        margin: 0 4vh;
        display: flex;
        flex-flow: column nowrap;
        align-items: center;
        justify-content: center;
        opacity: 0;
        .album-cover {
            height: 30vh;
            width: 30vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            border: 1px solid white;
            .album-overlay {
                position: absolute;
                bottom: 0;
                left: 0;
                height: 110%;
                width: 110%;
                background: white;
                z-index: 4;
            }
            .play-button {
                position: absolute;
                bottom: 0;
                left: 0;
                height: 100%;
                width: 100%;
                background: rgba(9, 9, 9, 0.57);
                z-index: 4;
                display: flex;
                justify-content: center;
                align-items: center;
                opacity: 0;
                cursor: pointer;
                img {
                    width: 30%;
                    height: auto;
                }
            }
            img {
                height: auto;
                width: 120%;
            }
            &:hover {
                .play-button {
                    opacity: 1;
                    transition: all 0.3s ease-out;
                }
            }
        }
        .album-title {
            transform: translateY(4vh);
            h2 {
                font-family: 'Indie Flower';
                font-size: 1.2em;
                text-transform: uppercase;
                opacity: 0;
                cursor: pointer;
                &:hover {
                    color: rgb(128, 128, 128);
                }
            }
        }
        &:hover {
            .album-title {
                h2 {
                    opacity: 1;
                    transition: all 0.2s ease-out;
                }
            }    
        }
    }
</style>