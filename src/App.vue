<template>
  <div id="app-cv">
    <div class="panel-outline">
      <button @click="generateReport()">Download CV</button>

      <div class="outline">
        <h3>Outline</h3>
        <ul>
          <li>
            <a href="#Personal">PERSONAL DETAILS</a>
          </li>
          <li>
            <a href="#EDUCATIONAL_BACKGROUND">EDUCATIONAL BACKGROUND</a>
          </li>
          <li>
            <a href="#PROFESSIONAL_SUMMARY">PROFESSIONAL SUMMARY</a>
          </li>
          <li>
            <a href="#SOFTWARE">SOFTWARE</a>
          </li>
          <li>
            <a href="#OPERATING_SYSTEMS">OPERATING SYSTEMS</a>
          </li>
          <li>
            <a href="#SKILL_EXPERIENCE">SKILL EXPERIENCE</a>
          </li>
          <li>
            <a href="#PROFESSIONAL_EXPERIENCE">PROFESSIONAL EXPERIENCE</a>
          </li>
        </ul>
      </div>
    </div>
    <div ref="elHtml2Pdf">
      <CVTemplate />
    </div>
    <!-- <vue-html2pdf
      :show-layout="true"
      :float-layout="true"
      :enable-download="true"
      :preview-modal="false"
      filename="nguyen-van-hau-cv"
      :pdf-quality="2"
      :manual-pagination="true"
      pdf-format="a4"
      pdf-orientation="portrait"
      pdf-content-width="800px"
      @progress="onProgress($event)"
      @hasStartedGeneration="hasStartedGeneration()"
      @hasGenerated="hasGenerated($event)"
      ref="html2Pdf"
    >
      <section slot="pdf-content">
        
      </section>
    </vue-html2pdf> -->
  </div>
</template>

<script>
import html2pdf from "html2pdf.js";
import CVTemplate from "./components/CVTemplate.vue";

export default {
  name: "App",
  methods: {
    /*
            Generate Report using refs and calling the
            refs function generatePdf()
        */
    generateReport() {
      html2pdf()
        .from(this.$refs.elHtml2Pdf)
        .set(
          {
            margin: 0,
            filename: "nguyen-van-hau-cv.pdf",
            image: { type: "jpeg", quality: 0.98 },
            margin: [0.2, 0, 0.22, 0],
            html2canvas: { scale: 2 },
            jsPDF: { unit: "in", format: "a4", orientation: "portrait" },
          }
        )
        .save("nguyen-van-hau-cv.pdf")
        .catch((err) => {
          console.error(err);
        });
      // this.$refs.elHtml2Pdf.generatePdf();
    },
  },

  components: {
    CVTemplate,
  },
};
</script>

<style>
body,
html {
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
}

#app-cv {
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
  top: 0;
  left: 0;
}

#app-cv .panel-outline {
  position: fixed;
  z-index: 10000;
  width: 250px;
  height: 400px;
  left: 10px;
  top: 10px;
  background: #987;
  border: blue 1px solid;
  border-radius: 3px;
  text-align: center;
  padding: 5px;
}

#app-cv .panel-outline .outline,
#app-cv .panel-outline .outline h3 {
  text-align: left;
}

#app-cv .panel-outline .outline h3 {
  padding: 20px 0px 10px 0px;
}

#app-cv .panel-outline .outline ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

#app-cv .panel-outline .outline ul li {
  padding: 10px 5px;
}

#app-cv .panel-outline .outline ul a {
  color: blue;
  font-weight: 500;
}

@media only screen and (max-width: 600px) {
  #app-cv .panel-outline {
    width: 50px;
    height: 20px;
    left: 2px;
    top: 2px;
  }

  #app-cv .panel-outline * {
    display: none;
  }

  #app .panel-outline:hover {
    width: 250px;
    height: 400px;
    left: 10px;
    top: 10px;
  }

  #app-cv .panel-outline:hover * {
    display: unset;
  }
}
</style>
