<template>
    <div class="sidebar">
        <a href="https://www.soundcloud.com/dip-emotions" target="_blank"><img src="~assets/soundcloud.svg" alt="logo soundcloud"></a>
        <a href="https://www.youtube.com/channel/UCwyei_3VwNebQm1G11yJSRw" target="_blank"><img src="~assets/youtube.svg" alt="logo youtube"></a>
        <a href="https://www.instagram.com/amston.gtr" target="_blank"><img src="~assets/instagram.svg" alt="logo instagram"></a>
        <a href="https://www.facebook.com/AmstonBeats" target="_blank"><img src="~assets/facebook.svg" alt="logo soundcloud"></a>
    </div>
</template>

<script>
    export default {
        name: 'sideBar'
    }
</script>

<style lang="scss">
    .sidebar {
        height: 88vh;
        width: 8vw;
        background: white;
        display: flex;
        flex-flow: column nowrap;
        justify-content: flex-end;
        align-items: center;
        min-width: 83px;
        a {
            margin-bottom: 5vh;
            max-width: 30%;
              img {
                width: 100%;
                height: auto;
            }
            &:hover {
                filter: brightness(120%);
            }
        }
    }
</style>