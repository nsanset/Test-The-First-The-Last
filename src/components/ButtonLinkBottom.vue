<template>
  <div class="button-link-left">
    <button class="button">
      <router-link to="/about">{{textButtonBottom}}</router-link>
    </button>
  </div>
</template>

<script>

export default {
  name: 'ButtonLinkBottom',
  props: ['textButtonBottom']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.button-link-left{
  position: fixed;
  left: 50%;
  bottom: 30px;
  transform: translate(-50%, -50%);
  margin: 0 auto;
  z-index: 200;
}
.button {
  background: none;
  border: none;
  cursor: pointer;
  font-size: 16px;
  font-style: italic;
  font-weight: 500;
  a{
    color: #000;
    text-decoration: none;
    transition: .5s;
  }
}
.button > a:hover{
  color: #fff;
  transition: .5s;
}
a:before{
  content: '';
  width: 0;
  height: 3px;
  background-color: #fff;
  position: absolute;
  top: 100%;
  left: 0;
  transition: .5s;
}
.button:hover a:before{
  width: 100%;
  transition: .5s;
}

@media screen and (max-width: 575px) {
  .button-link-left{
    display: none;
  }
}
</style>
