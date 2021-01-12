<template>
  <div class="text-arrow" @click="$emit('clicked')">
      <p><slot></slot></p>
      <div class="line"></div>
      <div class="circle"></div>
  </div>
</template>

<script>
export default {
    name: 'textArrow'
}
</script>

<style lang="scss">
    .text-arrow {
        display: flex;
        flex-flow: column;
        justify-content: space-evenly;
        align-items: center;
        cursor: pointer;
        p {
            font-weight: 400;
            margin-bottom: 2vh;
        }
        .line {
            height: 5vh;
            width: 1.5px;
            background: #282828;
        }
        .circle {
            background: white;
            border: solid 1.5px #282828;
            border-radius: 50px ;
            height: 3vh;
            width: 3vh;
        }
    }
</style>