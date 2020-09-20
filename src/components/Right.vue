<template>
    <div class="right">
      <img src="../img/Iphone.png" alt="Iphone" class="image__iphone" />
      <div class="right__wrapper">
        <img src="../img/iPad Pro.jpg" alt="Ipad Pro" class="image__ipad">
      </div>
    </div>
</template>

<script>
export default {
  name: 'Right'
}
</script>

<style lang="scss">
  .right {
    position: relative;
    width: 38%;

    &__wrapper {
      overflow: hidden;
    }
  }
  .image__iphone {
    object-fit: cover;
    width: 249px;
    height: 513px;
    position: absolute;
    top: 15%;
    left: -17%;
  }

  .image__ipad {
    height: 660px;
    width: 1188px;
    margin: auto 0 auto 150px;
  }
</style>
