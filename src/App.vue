<template>
  <div id="app">
    <button @click="generateReport()">download CV</button>
    <vue-html2pdf
      :show-layout="true"
      :float-layout="true"
      :enable-download="true"
      :preview-modal="false"
      :paginate-elements-by-height="1400"
      filename="nguyen-van-hau-cv"
      :pdf-quality="2"
      :manual-pagination="false"
      pdf-format="a4"
      pdf-orientation="portrait"
      pdf-content-width="800px"
      @progress="onProgress($event)"
      @hasStartedGeneration="hasStartedGeneration()"
      @hasGenerated="hasGenerated($event)"
      ref="html2Pdf"
    >
      <section slot="pdf-content">
        <CVTemplate />
      </section>
    </vue-html2pdf>
  </div>
</template>

<script>
import VueHtml2pdf from "vue-html2pdf";
import CVTemplate from "./components/CVTemplate.vue";

export default {
  name: "App",
  methods: {
    /*
            Generate Report using refs and calling the
            refs function generatePdf()
        */
    generateReport() {
      this.$refs.html2Pdf.generatePdf();
    },
  },

  components: {
    CVTemplate,
    VueHtml2pdf,
  },
};
</script>

<style>
body,html{
    width: 100%;
    height: 100%;
    padding: 0;
    margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50; 
  background: #999;
  position: absolute;
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
  overflow: auto;
}
#app button{
  position: fixed;
  z-index: 10000;
}
</style>
