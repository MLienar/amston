<template>
  <div class="song-slider">
      <textArrow @mouse-over="previewSongs" @clicked="toggleSlider">my music</textArrow>
  </div>
</template>

<script>
import textArrow from '../common/textArrow'
const { gsap }  = require("gsap/dist/gsap")

export default {
    name: 'songSlider',
    data() {
        return {
            sliderIsOpen: false,
            tl: gsap.timeline( {paused: true} )
        }
    },
    components: {
        textArrow
    },
    mounted: function() {
            this.tl.addLabel("start")
            .to(".song-slider", 0.5, { transform:"translateX(-27vw)", height: "55vh"})
            .to(".overlay", 0.5, {display: "block", opacity: "0.5", backdropFilter:"blur(50px)"}, 0.2)
            .to(".text-arrow", 0.6, {color: "white"}, 0.2)
            .to(".line", 0.6, {background: "white"},0.1)
            .to(".circle", 0.6, {border: "2px white"}, 0.1)
    },
    methods: {
        previewSongs: function() {
            
            // let tl = gsap.timeline({ paused: true })
            // // add animations and labels to the timeline
            // tl.addLabel("start")
            // .to(".song-slider", { transform:"translateX(36vw)" })
        },
        toggleSlider() {    

            if (this.sliderIsOpen) {
                this.tl.reverse()
                this.sliderIsOpen = false
            } else {
                this.tl.play()
                this.sliderIsOpen = true
            }
        }
    }
}
</script>

<style lang="scss">
    .song-slider {
        background: white;
        height: 50vh;
        min-width: 80vw;
        margin-top: 10vh;
        display: flex;
        flex-flow: row nowrap;
        justify-content: flex-start;
        align-items: center;
        transform: translateX(40vw);
        z-index: 3;
        .text-arrow {
            transform: rotate(-90deg) translateY(-4vw);
            // &:hover {
            //     transform: rotate(-90deg) translateY(-6vw);
            //     transition: all 0.1s ease-out;
            //     .circle {
            //         width: 4vh;
            //         height: 4vh;
            //         transition: all 0.1s ease-out;
            //     }
            }
        }
        .close-slider {
            align-self: flex-start;
        }
        
</style>