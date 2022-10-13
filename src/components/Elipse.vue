<template>
  <div class="container">
    <div class="eclipse" :style="parralaxEclipse">
      <div class="circle-button">
        <svg viewBox="0 0 100 100" width="100" height="100">
          <defs>
            <path id="circle"
              d="
                M 50, 50
                m -37, 0
                a 37,37 0 1,1 74,0
                a 37,37 0 1,1 -74,0"/>
          </defs>
          <text font-size="10">
            <textPath xlink:href="#circle">
              {{circleButtonTitle}}
            </textPath>
          </text>
        </svg>
      </div>
    </div>
    <h1 :style="parralaxTitle" class="main-title">{{mainTitle}}</h1> 
  </div>
</template>

<script>
export default {
  name: 'Elipse',
  props: ['mainTitle', 'circleButtonTitle'],
  data() {
    return {
      x: 0,
      y: 0,
      viewportHeight: 1,
      viewportWidth: 1
    }
  },
  created () {
    this.updateViewportSize()
  },
  mounted () {
    document.addEventListener('mousemove', this.onMouseMove)
    window.addEventListener('resize', this.updateViewportSize)
  },
  unmounted () {
    document.removeEventListener('mousemove', this.onMouseMove)
    window.removeEventListener('resize', this.updateViewportSize)
  },
  computed: {
    parralaxEclipse () {
      return `transform: translate(${ percent(this.x, this.viewportWidth) }px, ${ percent(this.y, this.viewportHeight) }px)`
      function percent (value, total) {
        return Math.round((value * 100 / total - 50) / 3);
      }
    },
    parralaxTitle () {
      return `transform: translate(${ percent(this.x, this.viewportWidth) }px, ${ percent(this.y, this.viewportHeight) }px)`
      function percent (value, total) {
        return Math.round((value * 100 / total - 50));
      }
    }
  },

  methods: {
    onMouseMove (ev) {
      this.x = ev.clientX
      this.y = ev.clientY
    },
    updateViewportSize () {
      this.viewportHeight = window.innerHeight
      this.viewportWidth = window.innerWidth
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container{
  height: 100%;
  overflow: hidden;
  display: -webkit-box;
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  align-items: center;
}
.main-title{
  position: absolute;
  width: 60%;
  color: rgb(55,55,55);
  text-align: center;
  font-weight: 700;
  font-size: 82px;
  font-family: 'Grtsk Giga';
  font-weight: 800;
  font-style: normal;
  z-index: 138;
}
.eclipse {
  width: 600px;
  height: 600px;
  border-radius: 50%;
  background: radial-gradient(closest-side,#ffcb46,#ffcb46 75%,transparent 100%); 
  z-index: 136;
}
.circle-button{
  position: absolute;
  bottom: 15px;
  right: 15px;
  height: 150px;
  width: 150px;
  border-radius: 50%;
  cursor: pointer;
  z-index: 136;
  animation-name: rotateReverce; 
  animation-duration: 4s; 
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}
.circle-button:before {
  content: "\25CF";
  position: absolute;
  top: 50%;
  right: 50%;
  transform: translate(50%,-50%);
}
.circle-button:hover {
  animation-name: rotate; 
  animation-duration: 4s; 
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}
@keyframes rotate {
  from {transform: rotate(360deg);}
  to {transform: rotate(0deg);}
}
svg {
  fill: #fff;
  height: auto;
  max-width: 66vmin;
  transform-origin: center;
  width: 100%;
}

@media screen and (max-width: 1200px) {
  .main-title{
    width: 80%;
    font-size: 58px;
  }
}

@media screen and (max-width: 991px) {

}

@media screen and (max-width: 767px) {

}

@media screen and (max-width: 575px) {
  .eclipse{
    width: 350px;
    height: 350px;
  }
  .main-title{
    width: 100%;
    font-size: 34px;
  }
  .circle-button{
    bottom: -50px;
  }
}


</style>
