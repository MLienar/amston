<template>
  <div class="song-slider">
      <textArrow @mouse-over="previewSongs" @clicked="toggleSlider" @enter="previewSongs('enter')" @leave="previewSongs('leave')">my music</textArrow>
      <songBlock />
      <songBlock />
      <songBlock />
      <songBlock />
  </div>
</template>

<script>
import textArrow from '../common/textArrow'
import songBlock from './songBlock'
const { gsap }  = require("gsap/dist/gsap")

export default {
    name: 'songSlider',
    data() {
        return {
            sliderIsOpen: false,
            sliderTl: gsap.timeline( {paused: true} ),
            previewTl: gsap.timeline( {paused: true} )
        }
    },
    
    components: {
        textArrow,
        songBlock
    },
    mounted: function() {
            this.sliderTl.addLabel("start")
            .to(".song-slider", 0.8, { transform:"translateX(-27vw)", height: "55vh"})
            .to(".overlay", 0.5, {display: "block", opacity: "0.5", backdropFilter:"blur(50px)"}, 0.2)
            .to(".text-arrow", 0.6, {color: "white"}, 0.2)
            .to(".line", 0.6, {background: "white"},0.1)
            .to(".circle", 0.5, {width: "5vh", height: "5vh"}, 0.1)
            .to(".cross", 0.5, {opacity: 1}, 0.2)
            .to(".cross-1", 0.3, {transform: "rotate(45deg)"}, 0.6)
            .to(".cross-2", 0.3, {transform: "rotate(-45deg)"}, 0.4)
            .to(".circle", 0.1, {width: "5vh", height: "5vh"}, 0.1)
            .to(".song-block", 0.4, {opacity: 1, stagger: 0.1}, 0.1)
            .to(".album-overlay", 0.5, {height: "0%", stagger: 0.1}, 0.1)

            this.previewTl.addLabel("start")
            .to(".song-slider", 0.2, { transform:"translateX(40vw)", height: "51vh"})
            .to(".line", 0.2, {height: "6vh"},0.1 )
            .to(".circle", 0.2, { height: "4vh", width: "4vh"}, 0.1)

    },
    methods: {
        previewSongs: function(input) {
            if (!this.sliderIsOpen) {            
                if(input === 'enter') {
                    this.previewTl.play()
                } else if (input === 'leave'){
                    this.previewTl.reverse(1, false)
                }
            } 
        },

        toggleSlider() {    
            if (this.sliderIsOpen) {
                this.sliderTl.reverse()
                this.previewSongs('leave')
                setTimeout(() => {  this.sliderIsOpen = false }, 500)

            } else {
                this.sliderTl.play()
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
        transform: translateX(42vw);
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