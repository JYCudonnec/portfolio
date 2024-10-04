<template>
  <div id="app">
    <section id="homePage">
      <HomePage />
    </section>
    <section id="aboutMe">
      <AboutMe />
    </section>
    <section id="skillsAndTools">
      <SkillsAndTools />
    </section>
    <section id="websitesAndOther">
      <WebsitesAndOther />
    </section>
    <section id="contactForm">
      <ContactForm />
    </section>
  </div>
</template>

<script>
import HomePage from './components/HomePage.vue';
import AboutMe from './components/AboutMe.vue';
import SkillsAndTools from './components/SkillsAndTools.vue';
import WebsitesAndOther from './components/WebsitesAndOther.vue';
import ContactForm from './components/ContactForm.vue';

export default {
  name: 'App',
  components: {
    HomePage,
    AboutMe,
    SkillsAndTools,
    WebsitesAndOther,
    ContactForm
  },
  data() {
    return {
      isScrolling: false,
      scrollTimeout: null
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      if (this.scrollTimeout) {
        clearTimeout(this.scrollTimeout);
      }

      this.scrollTimeout = setTimeout(() => {
        this.isScrolling = false;
        this.repositionSections();
      }, 100);

      if (!this.isScrolling) {
        this.isScrolling = true;
      }
    },
    repositionSections() {
      const sections = document.querySelectorAll('section');
      const windowHeight = window.innerHeight;

      sections.forEach(section => {
        const rect = section.getBoundingClientRect();
        if (rect.top < windowHeight / 2 && rect.bottom > windowHeight / 2) {
          window.scrollTo({
            top: section.offsetTop,
            behavior: 'smooth'
          });
        }
      });
    }
  }
};
</script>

<style>
@import './assets/styles.css';

section {
  height: 100%; 
}
</style>