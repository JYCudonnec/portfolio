<template>
  <div class="section contact">
    <h1>Me Contacter</h1>
    <p>
      EMPORIATECH<br>
      110 rue de Fontenay<br>
      94300 Vincennes<br>
      06 81 92 19 26<br>
      contact@emporiatech.com<br>
    </p>
    <div class="cv-container">
      <img :src="cvPreviewUrl" alt="Aperçu du CV" class="cv-preview" />
      <br>
      <a href="/CV24.pdf" download class="download-button">Télécharger le CV</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactForm',
  data() {
    return {
      cvPreviewUrl: require('@/assets/CV24-appercu.png')
    };
  }
};
</script>

<style scoped>
.section.contact {
  padding: 20px;
  text-align: justify;
  background-color: #f1c40f;
  color: #2c3e50;
}
.section.contact h1 {
  margin: auto;
  background-color: #2c3e50;
  color: white;
  border-radius: 5px;
  text-align: center;
}
.section.contact p {
  text-align: center;
}
.cv-container {
  text-align: center;
  margin-top: 20px;
  margin: auto;
}
.cv-preview {
  max-width: 70%;
  max-height: 60vh;
  height: auto;
  border: 1px solid #2c3e50;
  border-radius: 5px;
}
.download-button {
  display: inline-block;
  margin-top: 10px;
  padding: 10px 20px;
  background-color: #2c3e50;
  color: white;
  text-decoration: none;
  border-radius: 5px;
  font-weight: bold;
}
.download-button:hover {
  background-color: #34495e;
}
</style>