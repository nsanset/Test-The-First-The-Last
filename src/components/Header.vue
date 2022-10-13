<template>
  <div class="header">
    <div id="lang">
      <nav class="header-navgtn">
        <div class="navbar-nav">
          <span>👅</span>
          <ul class="innernav">
            <li><a href="#">UA</a></li>
            <li><a href="#">EN</a></li>
          </ul>
        </div>
      </nav>
    </div>
    <div class="header-logo">
      <img src="@/assets/Union.svg"/>
    </div>
    <div class="mobile-menu">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Pro 6.2.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path d="M32 288c-17.7 0-32 14.3-32 32s14.3 32 32 32l384 0c17.7 0 32-14.3 32-32s-14.3-32-32-32L32 288zm0-128c-17.7 0-32 14.3-32 32s14.3 32 32 32l384 0c17.7 0 32-14.3 32-32s-14.3-32-32-32L32 160z"/></svg>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 24px 0;
  z-index: 99;
}
.mobile-menu{
  display: none;
}
.header-logo {
  text-align: center;
}
#lang {
  position: absolute;
  left: 35px;
  width: 50px;
  height: 50px;
  text-align: center;
  padding: 7px;
  border: 2px solid rgb(197,197,197);
  width: 40px;
  height: 40px;
  border-radius: 50%;
  cursor: pointer;
  .innernav li {
    height: 50px;
    list-style-type: none;
    font-size: 13px;
    color: #666;
    opacity: 0;
    visibility: hidden;
    transform: translate3d(0px, -12px, 0px);
    -webkit-transform: translate3d(0px, -12px, 0px);
    -moz-transform: translate3d(0px, -12px, 0px);
    
  }
  .header-navgtn, .navbar-nav {
    &.innernav li a {
      height: 50px;
      list-style-type: none;
      font-size: 13px;
      font-weight: 400;
      color: #666;
      padding: 15px 25px;
      display: inline-block;
      width: 100%;
      margin: 0px;
      color: red;
    }
    .navbar-nav:hover .innernav {
      position: absolute;
      border-radius: 15px;;
      top: 0px;
      left: 0px;
      height: 35px;
      width: 200px;
      opacity: 1;
      visibility: visible;
      transition: all 0.3s cubic-bezier(0.86,0,0.07,1);
      li {
        height: 35px;
        opacity: 1;
        visibility: visible;
        transition: all 0.3s cubic-bezier(0.86,0,0.07,1);
        &:nth-child(1) {
          position: absolute;
          top: 18px;
          left: 15px;
          display: inline-block;
          transition-delay: 180ms;
          transform: translate3d(30px, -10px, 0px);
        }
        &:nth-child(2) {
          position: absolute;
          top: 18px;
          left: 50px;
          display: inline-block;
          transition-delay: 280ms;
          transform: translate3d(30px, -10px, 0px);
        }
      }
    }
  }
}
.innernav li a{
  color: #000;
  text-decoration: none;
  font-style: italic;
  font-weight: 500;
}
.innernav li a:hover{
  color: #fff;
  transition: .3s;
}
@media screen and (max-width: 575px) {
  .mobile-menu{
    display: block;
    position: absolute;
    right: 15px;
    top: 25px;
    width: 25px;
  }
}

</style>
