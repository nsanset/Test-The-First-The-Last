<template>
  <div class="home">
    <Header/>
    <RunText :runText="runText" />
    <Elipse :mainTitle="mainTitle" :circleButtonTitle="circleButtonTitle"/>
    <ButtonLinkLeft :textButtonLeft="textButtonLeft"/>
    <ButtonLinkBottom :textButtonBottom="textButtonBottom"/>
    <ButtonLinkRight :textButtonRight="textButtonRight"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import RunText from '@/components/RunText.vue'
import Elipse from '@/components/Elipse.vue'
import ButtonLinkLeft from '@/components/ButtonLinkLeft.vue'
import ButtonLinkBottom from '@/components/ButtonLinkBottom.vue'
import ButtonLinkRight from '@/components/ButtonLinkRight.vue'

export default {
  name: 'Home',
  components: {
    Header,
    RunText,
    Elipse,
    ButtonLinkLeft,
    ButtonLinkBottom,
    ButtonLinkRight
  },
  data() {
      return {
        mainTitle: 'FULL-CYCLE EVENT AGENCY',
        circleButtonTitle: 'showreel showreel showreel',
        runText: 'FULL-CYCLE EVENT AGENCY FULL-CYCLE EVENT AGENCY',
        textButtonLeft: 'where?',
        textButtonBottom: 'who?',
        textButtonRight: 'what?'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.home {
  position: relative;
  background-color: rgb(190,190,190);
  height: 100vh;
  width: 100%;
  overflow: hidden;
}
</style>
