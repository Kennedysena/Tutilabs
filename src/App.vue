<script setup>
import HelloWorld from './components/Home.vue'
import Header from './components/Header.vue'
import Subtitle from './components/Subtitle.vue'
import SubtitleTwo from './components/Subtitletwo.vue'
import Buttonfront from './components/Buttonfront.vue'
import Buttonback from './components/Buttonback.vue'
import GoodLook from './components/Goodlook.vue'
import Description from './components/Description.vue'
import Carouseltech from './components/Carouseltech.vue'
import About from './components/About.vue'
import Divbutton from './components/Divbutton.vue'
import ContainerOne from './components/ContainerOne.vue'
import Welcome from './components/Welcome.vue'
import Home from './components/Home.vue'
import CarouseltechBack from './components/CarouseltechBack.vue'
</script>

<template>
  <Header />
  <div style="display: flex; gap: 0.4rem;">
    <div style="display: flex; flex-direction: column; align-items: flex-start;">
      <Welcome />
      <Subtitle />
      <SubtitleTwo />
      <div style="display: flex; margin: 0 0 0.940rem 0.5rem;">
        <Buttonfront :key="activeButton" @click="activateCarousel" :class="{ inactive: activeButton === 'back' }" />
        <Buttonback :key="activeButton" @click="activateCarouselBack" :class="{ inactive: activeButton === 'front' }" />
      </div>
      <Carouseltech v-if="carouselActive" ref="carousel" @click="updateTechName(carousel.techname)"
        @update-description="updateDescription" @update-techname="updateTechName" />
      <CarouseltechBack v-if="carouselBackActive" ref="carouselBack" @update-description-back="updateDescriptionBack"
        @update-techname-back="updateTechNameBack" />

    </div>

    <div style="display: flex; flex-direction: column; align-items: flex-start;">
      <GoodLook />
      <div class="texto-e-info" style="display: flex; flex-direction: row; gap: 22px">
        <Description ref="descriptionComponent" :description="carouselActive ? description : descriptionBack"
          :techname="carouselActive ? techname : technameBack" />
        <About />
      </div>
    </div>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<script>
export default {
  components: {
    HelloWorld,
    Header,
    Subtitle,
    SubtitleTwo,
    Buttonfront,
    Buttonback,
    GoodLook,
    Description,
    Carouseltech,
    About,
    Divbutton,
    ContainerOne,
    Welcome,
    CarouseltechBack,
  },
  data() {
    return {
      carouselActive: true,
      carouselBackActive: false,
      description: '',
      techname: '',
      descriptionBack: '',
      technameBack: '',
      activeButton: 'front'
    }
  },
  methods: {
    activateCarousel() {
      this.carouselActive = true;
      this.carouselBackActive = false;
      this.activeButton = 'front';
      this.description = '';
      this.techname = '';
    },
    activateCarouselBack() {
      this.carouselActive = false;
      this.carouselBackActive = true;
      this.activeButton = 'back';
      this.descriptionBack = '';
      this.technameBack = '';
    },
    updateDescription(description,) {
      this.description = description;
    },
    updateTechName(techname) {
      this.techname = techname;
    },
    updateDescriptionBack(descriptionBack) {
      this.descriptionBack = descriptionBack;
    },
    updateTechNameBack(technameBack) {
      this.technameBack = technameBack;
    },


  }

}
</script>
