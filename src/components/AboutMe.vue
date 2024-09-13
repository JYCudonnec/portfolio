<template>
  <div class="section about">
    <h1>À Propos De Moi</h1>
    <div class="about-content">
      <div class="about-text">
      <p><b>J'ai 38 ans et suis actuellement en poste à EMPORIATECH.<br>J'ai une expertise solide en Wordpress, mais pas seulement. <br>Mon expérience inclut la création de sites sécurisés et performants, ainsi que la mise en place de boutiques en ligne et le développement de plugins personnalisés.</b>
      </p>
    </div>
    <div class="sliders">
      <div class="slider-container">
        <swiper
          ref="mainSwiper"
          :slides-per-view="1"
          :space-between="100"
          @swiper="onMainSwiper"
          @slideChange="onMainSlideChange"
        >
          <swiper-slide v-for="(slide, index) in slides" :key="index">
            <div class="slide-content">
              <font-awesome-icon :icon="['fas', slide.icon]" class="fa-icon"/>
              <h2>{{ slide.title }}</h2>
              <p v-html="slide.text"></p>
            </div>
          </swiper-slide>
        </swiper>
      </div>
      <div class="timeline-container">
        <swiper
          ref="timelineSwiper"
          :slides-per-view="3"
          :space-between="20" 
          @swiper="onTimelineSwiper"
          @slideChange="onTimelineSlideChange"
        >
          <swiper-slide v-for="(event, index) in timelineEvents" :key="index" @click="handleSlideTo(index)">
            <div class="timeline-event">
              <div class="timeline-title">{{ event.title }}</div>
              <div class="timeline-point"></div>
              <div class="timeline-year">
                <span v-if="event.year.includes('-')">
                  <span>{{ event.year.split('-')[0] }}</span>
                  <span>-</span>
                  <span>{{ event.year.split('-')[1] }}</span>
                </span>
                <span v-else>{{ event.year }}</span>
              </div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/swiper-bundle.css';
import 'swiper/css';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { library } from '@fortawesome/fontawesome-svg-core';
import { faLaptopCode, faChalkboardTeacher, faUserGraduate, faStethoscope, faDna, faUtensils, faGraduationCap, faCode } from '@fortawesome/free-solid-svg-icons';

library.add(faLaptopCode, faChalkboardTeacher, faUserGraduate, faStethoscope, faDna, faUtensils, faGraduationCap, faCode);

export default {
  name: 'AboutMe',
  components: {
    Swiper,
    SwiperSlide,
    FontAwesomeIcon,
  },
  data() {
    return {
      slides: [
        {
          icon: 'graduation-cap',
          title: 'Baccalauréat',
          text: 'Bac série S option Maths<br><i>Lycée Félix Le Dantec, Lannion (22)</i>',
        },
        {
          icon: 'stethoscope',
          title: 'PCEM',
          text: 'Premier Cycle Élémentaire de Médecine<br><i>Faculté de Médecine de de Brest (29)</i>',
        },
        {
          icon: 'dna',
          title: 'Licence de biologie',
          text: 'Parcours biologie cellulaire et Physiologie<br><i>Université Catholique de l\'Ouest (UCO), Guingamp (22)</i>',
        },
        {
          icon: 'utensils',
          title: 'Restauration',
          text: 'Serveur et commis de cuisine en hotellerie et restauration<br><i>L\'Agapa *****, Perros-Guirec (22)</i>',
        },
        {
          icon: 'truck-medical',
          title: 'Métiers du paramédical',
          text: 'Stages d\'ambulancier et de préparateur en pharmacie<br><i>Côtes d\'Armor (22)</i>',
        },
        {
          icon: 'person-chalkboard',
          title: 'Assistant d\'éducation',
          text: 'Encadrement des lycéens, vie scolaire, internat, aide au devoir, Bac, etc<br><i>Lycée Auguste Pavie, Guingamp (22)</i>',
        },
        {
          icon: 'code',
          title: 'Diplôme de développeur web',
          text: 'Formation de développeur web<br><i>IUT de Lannion (22)</i>',
        },
        {
          icon: 'laptop-code',
          title: 'Développeur Web',
          text: 'Création et maintenance de sites et applications web<br><i>Emporiatech, remote</i>',
        },
      ],
      timelineEvents: [
        { year: '2004', title: 'Baccalauréat' },
        { year: '2004-2006', title: 'PCEM' },
        { year: '2006-2009', title: 'Licence de Biologie' },
        { year: '2008-2010', title: 'Restauration' },
        { year: '2011-2012', title: 'Métiers du paramédical' },
        { year: '2012-2018', title: 'ASEN' },
        { year: '2020', title: 'Diplome Dev Web' },
        { year: '2020-2024', title: 'Developpeur Web' },
      ],
      mainSwiper: null,
      timelineSwiper: null,
    };
  },
  methods: {
    onMainSwiper(swiper) {
      this.mainSwiper = swiper;
    },
    onTimelineSwiper(swiper) {
      this.timelineSwiper = swiper;
    },
    onMainSlideChange() {
      if (this.timelineSwiper) {
        this.timelineSwiper.slideTo(this.mainSwiper.activeIndex-1);
      }
    },
    onTimelineSlideChange() {
      if (this.mainSwiper) {
        this.mainSwiper.slideTo(this.timelineSwiper.activeIndex+1);
      }
    },
    handleSlideTo(index) {
      if (this.timelineSwiper) {
        this.timelineSwiper.slideTo(index-1);
      }
      if (this.mainSwiper) {
        this.mainSwiper.slideTo(index);
      }
    },
  },
  mounted() {
    const lastIndex = this.timelineEvents.length;
    if (this.timelineSwiper) {
      this.timelineSwiper.slideTo(lastIndex);
    }
    if (this.mainSwiper) {
      this.mainSwiper.slideTo(lastIndex);
    }
  },
};
</script>

<style scoped>
.section.about {
  padding: 20px;
  text-align: justify;
  background-color: #2c3e50;
  color: white;
}
.section.about p {
  font-size: 0.9em;
  max-width: 600px;
  margin: auto;
  text-align: justify;
}
.section.about h1 {
  margin: auto;
  background-color: #f1c40f;
  color: #2c3e50;
  border-radius: 5px;
  text-align: center;
}
.slider-container {
  margin-top: 20px;
}
.timeline-container {
  margin-top: 0px;
  position: relative;
}
.timeline-container::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: #f1c40f;
  z-index: 1;
}
.slide-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
.slide-content .fa-icon {
  font-size: 3rem;
  color: #f1c40f;
  margin-bottom: 10px;
}
.slide-content h2 {
  margin-top: 0px;
  color: #f1c40f;
  margin-bottom: 0;
}
.slide-content p {
  margin-top: 5px;
  color: white;
}
.timeline-event {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  position: relative;
  z-index: 2;
  height: 100px;
  width: 100%;
}
.timeline-title {
  margin-bottom: 0px;
  color: #f1c40f;
  height: 40px; 
  display: flex;
  align-items: center; 
  font-weight: bold; 
  font-size: 0.9em;
}
.timeline-point {
  width: 10px;
  height: 10px;
  background-color: #f1c40f;
  border-radius: 50%;
  margin-bottom: 10px;
  position: absolute;
  top: 50%; 
  transform: translateY(-50%);
}
.timeline-year {
  margin-top: auto;
  color: white;
  position: absolute;
  bottom: 0px; 
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 0.8em;
  overflow: visible;
}
.timeline-year span {
  display: block;
  margin: 0; 
  line-height: 0.8; 
}
.about-text {
  font-size: 1em;
}
.sliders {
  font-size: 2.3vh;
  max-width : 800px;
  margin: auto;
}
@media (min-height: 600px) {
  .about-text {
    margin: 80px 0;
    font-size: 2.5vh;
    text-align: justify;
  }
}
</style>