<template>
  <div class="section skills">
    <h1>Mes Compétences</h1>
    <div class="skills-content">
      <div class="tasks">
        <ul>
          <li>Développement Full-Stack</li>
          <li>Conception de sites web responsives</li>
          <li>Optimisation SEO</li>
          <li>Création de thèmes/plugins personnalisés</li>
          <li>Intégration de maquettes</li>
          <li>Création de boutiques en ligne</li>
        </ul>
      </div>
      <div class="tags">
        <div class="language">
          <span>PHP
            <div class="hs-tooltip">PHP est un langage de script utilisé principalement pour le développement web côté serveur.</div>
          </span>
          <span>SQL
            <div class="hs-tooltip">SQL est un langage de programmation utilisé pour gérer et manipuler des bases de données.</div>
          </span>
          <span>HTML
            <div class="hs-tooltip">HTML est le langage standard utilisé pour créer des pages web.</div>
          </span>
          <span>CSS
            <div class="hs-tooltip">CSS est un langage de style utilisé pour décrire la présentation des documents HTML.</div>
          </span>
          <span>JavaScript
            <div class="hs-tooltip">JavaScript est un langage de programmation utilisé pour créer des contenus web interactifs.</div>
          </span>
          <span>TypeScript
            <div class="hs-tooltip">TypeScript est un sur-ensemble de JavaScript qui ajoute des types statiques.</div>
          </span>
          <span>Python
            <div class="hs-tooltip">Python est un langage de programmation polyvalent et facile à apprendre.</div>
          </span>
        </div>
        <div class="framework">
          <span>Laravel
            <div class="hs-tooltip">Laravel est un framework PHP pour le développement d'applications web.</div>
          </span>
          <span>React
            <div class="hs-tooltip">React est une bibliothèque JavaScript pour construire des interfaces utilisateur.</div>
          </span>
          <span>React Native
            <div class="hs-tooltip">React Native est un framework pour construire des applications mobiles en utilisant React.</div>
          </span>
          <span>Vue.js
            <div class="hs-tooltip">Vue.js est un framework JavaScript pour construire des interfaces utilisateur.</div>
          </span>
          <span>PhpSlim
            <div class="hs-tooltip">PhpSlim est un micro-framework PHP pour créer des applications web simples et rapides.</div>
          </span>
        </div>
        <div class="tool">
          <span>VS Code
            <div class="hs-tooltip">VS Code est un éditeur de code source développé par Microsoft.</div>
          </span>
          <span>Filezilla
            <div class="hs-tooltip">Filezilla est un client FTP pour transférer des fichiers entre un ordinateur et un serveur.</div>
          </span>
          <span>MAMP
            <div class="hs-tooltip">MAMP est une solution locale de serveur web pour macOS et Windows.</div>
          </span>
          <span>Postman
            <div class="hs-tooltip">Postman est un outil pour tester les API.</div>
          </span>
          <span>Docker
            <div class="hs-tooltip">Docker est une plateforme pour développer, expédier et exécuter des applications dans des conteneurs.</div>
          </span>
          <span>Git
            <div class="hs-tooltip">Git est un système de contrôle de version pour suivre les modifications du code source.</div>
          </span>
          <span>Procreate
            <div class="hs-tooltip">Procreate est une application de dessin numérique et retouche pour iPad.</div>
          </span>
        </div>
        <div class="cms">
          <span>WordPress
            <div class="hs-tooltip">WordPress est un système de gestion de contenu (CMS) utilisé pour créer des sites web.</div>
          </span>
        </div>
      </div>
      <div class="fa-icons">
        <div>
          <font-awesome-icon :icon="['fas', 'chart-line']" class="fa-icon"/>
          <div class="ss-tooltip">Capacité d'analyse</div>
        </div>
        <div>
          <font-awesome-icon :icon="['fas', 'graduation-cap']" class="fa-icon"/>
          <div class="ss-tooltip">Formation continue</div>
        </div>
        <div>
          <font-awesome-icon :icon="['fas', 'users']" class="fa-icon"/>
          <div class="ss-tooltip">Travail en équipe</div>
        </div>
        <div>
          <font-awesome-icon :icon="['fas', 'bolt']" class="fa-icon"/>
          <div class="ss-tooltip">Réactivité</div>
        </div>
        <div>
          <font-awesome-icon :icon="['fas', 'tools']" class="fa-icon"/>
          <div class="ss-tooltip">Résolution de problème</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SkillsAndTools',
  mounted() {
    this.adjustTooltips();
    window.addEventListener('resize', this.adjustTooltips);
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.adjustTooltips);
  },
  methods: {
    adjustTooltips() {
      const spans = this.$el.querySelectorAll('span');
      spans.forEach(span => {
        const rect = span.getBoundingClientRect();
        const hsTooltip = span.querySelector('.hs-tooltip');
        if (rect.left < 30) {
          hsTooltip.classList.add('hs-tooltip-right');
          hsTooltip.classList.remove('hs-tooltip-left');
        } else if (window.innerWidth - rect.right < 50) {
          hsTooltip.classList.add('hs-tooltip-left');
          hsTooltip.classList.remove('hs-tooltip-right');
        } else {
          hsTooltip.classList.remove('hs-tooltip-right');
          hsTooltip.classList.remove('hs-tooltip-left');
        }
      });
    }
  }
};
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');

.section.skills {
  text-align: left;
  padding: 20px;
  background-color: #f1c40f;
  color: #2c3e50;
}
.section.skills h1 {
  margin: auto;
  background-color: #2c3e50;
  color: white;
  border-radius: 5px;
  text-align: center;
}
.section.skills li {
  font-size: smaller;
  font-weight: bold;
  list-style: square;
  margin-left: -25px;
}
.section.skills h3 {
  font-size: 1em;
}
.section.skills .tags div {
  font-size: 1em;
  display: flex;
  flex-wrap: wrap;
}
.section.skills .tags .language span {
  background-color: rgb(215, 116, 17);
  position: relative;
}
.section.skills .tags .tool span {
  background-color: rgb(17, 83, 215);
  position: relative;
}
.section.skills .tags .cms span {
  background-color: rgb(21, 171, 73);
  position: relative;
}
.section.skills .tags .framework span {
  background-color: rgb(17, 129, 215);
  position: relative;
}
.section.skills span {
  font-size: smaller;
  border: 1px solid #000;
  margin: 5px;
  padding: 5px;
  border-radius: 5px;
  color: white;
  font-weight: bold;
  cursor: pointer;
}
.hs-tooltip {
  visibility: hidden;
  width: 200px;
  background-color: rgb(255, 255, 255);
  color: #000000;
  text-align: center;
  border-radius: 6px;
  padding: 5px;
  position: absolute;
  z-index: 1;
  bottom: 125%;
  left: 50%;
  margin-left: -100px;
  opacity: 0;
  transition: opacity 0.3s;
}

.hs-tooltip::after {
  content: "";
  position: absolute;
  top: 100%;
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: rgb(255, 255, 255) transparent transparent transparent;
}

span:hover .hs-tooltip {
  visibility: visible;
  opacity: 1;
}
.hs-tooltip-right {
  bottom: auto;
  left: 100%;
  margin-left: 10px;
  top: 50%;
  transform: translateY(-50%);
}

.hs-tooltip-right::after {
  top: 50%;
  left: -10px;
  margin-left: 0;
  margin-top: -5px;
  border-color: transparent rgb(255, 255, 255) transparent transparent;
}

.hs-tooltip-left {
  bottom: auto;
  left: -120px;
  margin-right: 0px;
  top: 50%;
  transform: translateY(-50%);
}
.hs-tooltip-left::after {
  top: 50%;
  left: -15px;
  margin-left: 225px;
  margin-top: -5px;
  border-color: transparent transparent transparent rgb(255, 255, 255);
}
.fa-icons {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin-top: 20px;
}
.fa-icons div {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 3px;
  width: 100%;
  padding: 10px;
  margin: 2px;
  background-color: #2c3e50;
}
.fa-icon {
  font-size: 1.9em;
  color: white;
}
.ss-tooltip {
  visibility: hidden;
  width: 100px !important;
  background-color: rgb(255, 255, 255);
  color: #000000;
  text-align: center;
  border-radius: 6px;
  padding: 5px;
  position: absolute;
  z-index: 1;
  opacity: 0;
  transition: opacity 0.3s;
  transform: translateY(-150%);
  font-size: 0.8em;
  font-weight: bold;
  line-height: 1.2em;
  height: calc(1.2em * 2);
  padding: 4px !important;
}
.ss-tooltip::after {
  content: "";
  position: absolute;
  top: 100%;
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: rgb(255, 255, 255) transparent transparent transparent;
}
.fa-icons div:hover .ss-tooltip {
  visibility: visible;
  opacity: 1;
  background-color: white;
}
.skills-content {
  height: 100%;
  max-width: 550px;
  margin: auto;
  /* display: flex;
  flex-direction: column;
  justify-content: space-evenly; */
}
@media (min-height: 600px) {
  .skills-content>div {
    margin: 2vh 0;
  }
  .skills-content .tags div{
    font-size: 2vh;
    justify-content: center;
  }
  .tasks {
    font-size: 3vh;
  }
}
@media (min-width: 600px) {
  .section.skills span {
    font-size: 2vw;
  }
}
@media (min-width: 800px) {
  .section.skills span {
    font-size: large;
  }
}
@media (min-height: 601px) and (min-width: 801px) {
  .skills-content>div {
    margin: 8vh 0;
  }
}
</style>