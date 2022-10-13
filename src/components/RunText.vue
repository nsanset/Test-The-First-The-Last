<template>
  <div>
    <div class='top-text-reverse'>
      <svg xmlns="http://www.w3.org/2000/svg">
        <text x="0" y="70">
        </text>
      </svg>
      <svg xmlns="http://www.w3.org/2000/svg" >
        <text x="0" y="50">
          {{runText}}
          {{runText}}
          {{runText}}
        </text>
      </svg>
    </div>
    <div class='top-text'>
      <svg xmlns="http://www.w3.org/2000/svg">
        <text x="0" y="70">
        </text>
      </svg>
      <svg xmlns="http://www.w3.org/2000/svg" >
        <text x="0" y="50">
          {{runText}}
          {{runText}}
          {{runText}}
        </text>
      </svg>
    </div>
    
  </div>
  

</template>

<script>
export default {
  name: 'RunText',
  props: ['runText']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.top-text, .top-text-reverse {
  width: calc(100vh + 100vw);
  font-family: 'Grtsk Giga';
  font-weight: 600;
  font-size: 52px;
  position: absolute;
  top: 0px;
  left: 0;
  right: 0;
  transform: rotate(-25deg) translateY(110px) translateX(-220px);
  svg {
    display: block;
    width: 100%;
    height: auto;
    text {
      fill: #bebecb;
    }
    &:nth-child(2) {
      text:nth-child(1) {
        animation: scrollTextStart 35s infinite linear;
        opacity: 0.2;
        stroke: #000;
      }
      text:nth-child(2) {
        animation: scrollTextEnd 35s infinite linear;
        opacity: 0.2;
        stroke: #000;
      }
    }

  }
}
.top-text-reverse{
  transform: rotate(-25deg) translateY(100px) translateX(-200px) scale(-1, -1);
}
@keyframes scrollTextStart {
  from { transform: translateX(0%); }
  to { transform: translateX(-100%); }
}
@keyframes scrollTextEnd {
  from { transform: translateX(100%); }
  to { transform: translateX(0); }
}

@media screen and (max-width: 1200px) {
  .top-text {
    transform: rotate(-38deg) translateY(-40px) translateX(-280px);
  }
  .top-text-reverse{
    transform: rotate(-38deg) translateY(-60px) translateX(-280px) scale(-1, -1);
  }

}


@media screen and (max-width: 991px) {
  .top-text {
    transform: rotate(-50deg) translateY(-145px) translateX(-410px);
  }
  .top-text-reverse{
    transform: rotate(-50deg) translateY(-150px) translateX(-410px) scale(-1, -1);
  }
}

@media screen and (max-width: 767px) {

}

@media screen and (max-width: 375px) {
  .top-text, .top-text-reverse {
    font-size: 28px;
  }
  .top-text {
    transform: rotate(-62deg) translateY(-230px) translateX(-320px);
  }
  .top-text-reverse{
    transform: rotate(-62deg) translateY(-180px) translateX(-320px) scale(-1, -1);
  }

}


</style>
