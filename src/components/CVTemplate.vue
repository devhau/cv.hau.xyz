<template>
  <div class="my-cv">
    <h2 class="title">{{ Personal.name }} - CV</h2>
    <CVPersonal :data="{ ...Personal }" />
    <CVBlock
      :data="{ ...EDUCATIONAL_BACKGROUND }"
      :key="EDUCATIONAL_BACKGROUND.Title"
    />
    <CVBlock
      :data="{ ...PROFESSIONAL_SUMMARY }"
      :key="PROFESSIONAL_SUMMARY.Title"
    />
    <CVBlock :data="{ ...SOFTWARE }" :key="SOFTWARE.Title" />
    <CVBlock :data="{ ...OPERATING_SYSTEMS }" :key="OPERATING_SYSTEMS.Title" />
    <div class="cv-block">
      <h3 class="title">PROFESSIONAL EXPERIENCE</h3>
      <div class="content">
        <CVProject
          v-for="item in PROFESSIONAL_EXPERIENCE"
          :key="item"
          :data="item"
        />
      </div>
    </div>
  </div>
</template>
<script>
import CVPersonal from "./CVPersonal.vue";
import CVBlock from "./CVBlock.vue";
import CVProject from "./CVProject.vue";
import configs from "./../configs";
export default {
  data() {
    return {
      Personal: {
        name: configs.name,
        PERSONAL_DETAILS: configs.PERSONAL_DETAILS,
      },
      EDUCATIONAL_BACKGROUND: {
        Title: "EDUCATIONAL BACKGROUND",
        Item: configs.EDUCATIONAL_BACKGROUND,
        Type: 0,
      },
      PROFESSIONAL_SUMMARY: {
        Title: "PROFESSIONAL SUMMARY",
        Item: configs.PROFESSIONAL_SUMMARY,
        Type: 0,
      },
      SOFTWARE: {
        Title: "SOFTWARE",
        Item: configs.SOFTWARE,
        Type: 1,
      },
      OPERATING_SYSTEMS: {
        Title: "OPERATING SYSTEMS",
        Item: configs.OPERATING_SYSTEMS,
        Type: 0,
      },
      PROFESSIONAL_EXPERIENCE: configs.PROFESSIONAL_EXPERIENCE,
    };
  },
  components: {
    CVPersonal,
    CVBlock,
    CVProject,
  },
};
</script>
<style scoped>
.my-cv {
  margin: 20px auto;
  width: 100%;
  max-width: 960px;
  min-height: 600px;
  min-height: 300px;
  background: #fff;
  border-radius: 3px;
  border: crimson;
  box-shadow: forestgreen 3px 5px;
}
.my-cv h2.title {
  text-transform: uppercase;
  text-align: center;
  padding: 15px 0px;
}
</style>
<style>
h3 {
  margin: 0;
  padding: 0;
}
.my-cv .cv-block {
  padding: 20px;
}
.my-cv .cv-block ul {
  margin: 0;
  padding: 0;
}
.my-cv table tr td,
.my-cv .cv-block ul li {
  padding: 5px 10px;
}
.my-cv table.border-bottom tr {
  border-bottom: tan 2px solid;
}
.my-cv h3.title {
  display: inline;
  padding: 5px;
  border-bottom: #302 3px solid;
}
.my-cv .content {
  padding: 5px 5px 0px 20px;
  margin-top: 15px;
}
</style>