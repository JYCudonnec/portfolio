<template>
  <div class="section home">
    <div class="header">
      <img :src="avatarSrc" alt="Avatar" class="avatar">
      <div class="bubble-div">
      <div class="bubble"></div>
    </div>
    </div>
    <div class="introduction">
      <h1 class="welcome-text">Bienvenue sur mon portfolio,</h1>
      <h2 class="im-text">je m'appelle</h2>
      <h2 class="name-text">Jean-Yves Cudonnec</h2>
      <h3 class="role-text">je suis Développeur Web</h3>
    </div>
    <div class="nav-buttons">
      <div class="nav-row">
        <div><a href="#aboutMe"><span>À propos de moi</span></a></div>
        <div><a href="#skillsAndTools"><span>Mes compétences</span></a></div>
      </div>
      <div class="nav-row">
        <div><a href="#websitesAndOther"><span>Mes réalisations</span></a></div>
        <div><a href="#contactForm"><span>CV & Contact</span></a></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      avatarSrc: require('@/assets/avatar.png')
    };
  },
  mounted() {
    this.generateKeyframes();
  },
  methods: {
    generateKeyframes() {
      const styleSheet = document.styleSheets[0];
      const keyframes = `@keyframes deform {
        ${Array.from({ length: 101 }, (_, i) => {
          const randomRadius = () => `${Math.random() * 20 + 50}%`;
          return `${i}% {
            border-radius: ${randomRadius()} ${randomRadius()} ${randomRadius()} ${randomRadius()} / ${randomRadius()} ${randomRadius()} ${randomRadius()} ${randomRadius()};
            transform: scale(${1 + Math.random() * 0.1});
          }`;
        }).join('\n')}
      }`;

      styleSheet.insertRule(keyframes, styleSheet.cssRules.length);
    }
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Grandstander&display=swap');

.section.home {
  text-align: center;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.avatar {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  margin-bottom: 20px;
  position: absolute;
  left: calc(50% - 75px);
  top: 40px;
  z-index: 10;
}

.welcome-text, .name-text, .role-text, .im-text {
  font-family: 'Grandstander', cursive;
}

.welcome-text, .im-text, .role-text {
  font-size: 1.2em;
  font-weight: lighter;
  margin: 10px 0;
}
.im-text {
  margin: 5% 0;
}

.name-text {
  font-size: 1.5em;
  margin: 5vh 0;
}

.bubble-div {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 200px;
}

.bubble {
  width: 200px;
  height: 200px;
  background-color: #2c3e50;
  border-radius: 50%;
  animation: deform 100s infinite;
  -webkit-animation-timing-function: linear; 
  animation-timing-function: linear;
}

.nav-buttons {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
  margin-bottom: 10%;
}

.nav-row {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin: 10px 0;
  width: 100%;
}

.nav-row div {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 0;
  padding: 0px 0px;
  background-color: #2c3e50;
  border-radius: 5px;
  cursor: pointer;
  height: 50px;
  width: 45%;
  min-width: 45%;
  max-width: 45%;
}

.nav-row div a {
  color: white;
  text-decoration: none;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.nav-row div span {
  font-weight: bold;
  font-size: medium;
  padding: 10px;
}
.introduction {
  font-size: 3vh;
}
@media (min-height: 600px) {
  .nav-row div span {
    font-size: 2.5vh;
    padding: 10px;
  }
  .nav-row div {
    height: 10vh;
  }
}
</style>