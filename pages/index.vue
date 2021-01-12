<template>
    <div class="container">
        <navBar />
        <div class="main-content">
            <sideBar />
            <contentBox />
        </div>
    </div>
</template>

<script>

    import navBar from '../components/common/navBar'
    import sideBar from '../components/common/sideBar'
    import contentBox from '../components/home/contentBox'

    export default {
      components: {
        navBar,
        sideBar,
        contentBox
      }

    }
</script>

<style lang="scss">
  .main-content {
    background: linear-gradient(241.39deg, rgba(203, 243, 255, 0.66) 16.5%, rgba(217, 207, 255, 0.94) 38.65%, rgba(207, 234, 255, 0.728215) 63.24%, rgba(193, 107, 223, 0.43) 76.88%);
    height: 88vh;
    width: 100vw;
    display: flex;
    flex-flow: row nowrap;
  }
</style>
