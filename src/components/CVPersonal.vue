<template>
  <div class="cv-personal cv-block">
    <div class="col-info">
        <h3 class="title">PERSONAL DETAILS</h3>
        <div class="content">
            <table>
                <tr v-for="(value, key) in data.PERSONAL_DETAILS" :key="key+value">
                    <td style="font-weight:700">{{key}}</td>
                    <td style="font-weight:500">: {{value}}</td>
                </tr>
            </table>
        </div>
    </div>
    <div class="col-image">
        <img :src="data.Image">
    </div>
  </div>
</template>
<script>
export default {
    props: ['data']
}
</script>
<style scoped>
.cv-personal{
    display: flex;
    flex-direction: row;
    align-items: stretch;
}
.cv-personal .col-info{
    flex-grow: 3;
}
.cv-personal .col-image{
    flex-grow: 2;
    vertical-align: middle;
    position: relative;
    padding-top: 20px;
    min-width: 100px;
}
.cv-personal .col-image img{
    min-width: 100px;
    height:90%;
    max-height: 250px;
    border-radius: 2px;
}
</style>