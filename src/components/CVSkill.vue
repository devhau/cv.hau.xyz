<template>
  <div class="cv-block cv-skill">
    <h3 class="title" :id="DataId">{{ data.Title }}</h3>
    <div class="content">
    <div class="scroll-content">
      <table border="1">
        <tr>
          <td>Skill</td> <td v-for="(item,key) in data.Items" :key="'skill'+key">{{item.SKILL}}</td>
        </tr>
        <tr>
          <td>Experience</td> <td v-for="(item,key) in data.Items" :key="'EXPERIENCE'+key">{{item.EXPERIENCE}}</td>
        </tr>
        <tr>
          <td>Last Year</td> <td v-for="(item,key) in data.Items" :key="'LAST_YEAR'+key">{{item.LAST_YEAR}}</td>
        </tr>
      </table>
    </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["data","DataId"],
};
</script>
<style>
.scroll-content{
    width: 100%;
    overflow: auto;
    padding: 10px 5px;
}
</style>