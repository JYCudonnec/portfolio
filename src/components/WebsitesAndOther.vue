<template>
  <div class="section websites">
    <h1>Quelques réalisations</h1>
    <div class="grid-container">
      <div class="grid-item" @click="openUrl('https://www.hikamp.com')">
        <div class="item-content">
          <img :src="hikampSrc" alt="Hikamp Logo" class="grid-image">
          <p class="grid-text"><b>Site web spécialisé dans les randonnées</b><br><i>Wordpress - Plugin custom d'analyse de GPX - Création de boutique Woocommerce</i></p>
        </div>
        <div class="iframe-container">
          <iframe :src="hikampEmbed" class="grid-embed" frameborder="0"></iframe>
        </div>
      </div>
      <div class="grid-item" @click="openUrl('https://www.neuroprofiler.com')">
        <div class="item-content">
          <img :src="neuroSrc" alt="Neuroprofiler Logo" class="grid-image">
          <p class="grid-text"><b>Site de conseils en investissement</b><br><i>Wordpress - Thème personnalisé - Gestion multilangues</i></p>
        </div>
        <div class="iframe-container">
          <iframe :src="neuroEmbed" class="grid-embed" frameborder="0"></iframe>
        </div>
      </div>
      <div class="grid-item" @click="openUrl('https://www.b2ai.fr')">
        <div class="item-content">
          <img :src="b2aiSrc" alt="B2ai Logo" class="grid-image">
          <p class="grid-text"><b>Sytèmes connectés pour bâtiments intelligents</b><br><i>Wordpress - Intégration de maquettes & Édition de contenu</i></p>
        </div>
        <div class="iframe-container">
          <iframe :src="b2aiEmbed" class="grid-embed" frameborder="0"></iframe>
        </div>
      </div>
      <div class="grid-item" @click="openUrl('https://jycudonnec.github.io/running-order/')">
        <div class="item-content">
          <img :src="hellfestSrc" alt="Hellfest Logo" class="grid-image">
          <p class="grid-text"><b>Assistant de préparation de Running-Order</b><br><i>React - Système d'authentification via Discourse</i></p>
        </div>
        <div class="iframe-container">
          <iframe :src="hellfestEmbed" class="grid-embed" frameborder="0"></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WebsitesAndOther',
  data() {
    return {
      hikampSrc: require('@/assets/hikamp_logo.png'),
      neuroSrc: require('@/assets/neuroprofiler_logo.png'),
      b2aiSrc: require('@/assets/b2ai_logo.png'),
      hellfestSrc: require('@/assets/hellfest_logo.png'),
      hikampEmbed: 'https://www.hikamp.com',
      neuroEmbed: 'https://www.neuroprofiler.com',
      b2aiEmbed: 'https://www.b2ai.fr',
      hellfestEmbed: 'https://jycudonnec.github.io/running-order/',
    };
  },
  methods: {
    openUrl(url) {
      window.open(url, '_blank');
    }
  }
};
</script>

<style scoped>
.section.websites {
  text-align: left;
  padding: 20px;
  background-color: #2c3e50;
}
.section.websites h1 {
  margin: auto;
  background-color: #f1c40f;
  color: #2c3e50;
  border-radius: 5px;
  text-align: center;
}
.section.websites li {
  font-size: smaller;
}
.grid-container {
  display: grid;
  gap: 0px;
}

.grid-item {
  background-color: white;
  border-radius: 5px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px;
  border: 3px solid rgba(0, 162, 255, 0.7);
  cursor: pointer; /* Add cursor pointer to indicate clickable items */
}

.item-content {
  display: flex;
  align-items: center;
  width: 80%;
  margin-bottom: 10px;
}

.grid-image {
  width: 50px;
  height: 50px;
  margin-right: 10px;
}

.grid-text {
  flex: 1;
  font-size: smaller;
  text-align: left;
}

.iframe-container {
  width: 100%;
  max-width: 300px;
  height: 500px; /* Increase the height of the iframe container */
  overflow: hidden;
  position: relative;
}

.grid-embed {
  width: 100%;
  height: 100%;
  border: none;
  position: absolute;
  top: 0;
  left: 0;
  zoom: 0.3;
}

/* Media query for mobile devices */
@media (max-width: 600px) {
  .grid-container {
    grid-template-columns: 1fr;
  }
  .grid-item {
    height: auto; /* Adjust height to fit content */
  }
  .iframe-container {
    display: none;
  }
  .grid-item {
    margin: 1vh;
    padding: 0;
  }
  .item-content {
    width: 100%;
  }
}

/* Media query for larger screens */
@media (min-width: 601px) {
  .grid-container {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    height: calc(100vh - 65px);
  }
  .grid-item {
    height: calc(50vh - 120px); /* Adjust height to fit 2 items with gap */
    margin: 5%;
  }
}
</style>