<template>
  <div id="app">
    <vue-page-transition name="overlay-left-full">
      <router-view class="back" :key="$route.fullPath"/>
    </vue-page-transition>
  </div>
</template>

<style lang="scss">
@import './assets/fonts/GrtskGiga/stylesheet.css';
*{
  margin:0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Grtsk Giga Bkslnt';
}
.overlay-left,  .overlay-right,  .overlay-top,  .overlay-bottom   {
  background: #FFCB46 !important;
  z-index: 555 !important;
}

</style>

