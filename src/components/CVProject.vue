<template>
    <div class="cv-project">
        <h4 class="cv-project-title">
            {{data.Time}} ({{data.Experience_month}} Month) {{data.Experience}}
        </h4>
        <div class="cv-project-info">
            <table class="border-bottom">
                <tr>
                    <td style="font-weight:700">Project</td>
                    <td style="font-weight:500">{{data.Project_Name}} </td>
                </tr>
                <tr>
                    <td style="font-weight:700">Responsibilities</td>
                    <td style="font-weight:500">
                        <ul>
                            <li v-for="item in data.Responsibilities" :key="item"> {{item}}</li>
                        </ul>
                    </td>
                </tr>
                <tr>
                    <td style="font-weight:700">Technologies</td>
                    <td style="font-weight:500">
                        <ul>
                            <li v-for="item in data.Technologies" :key="item"> {{item}}</li>
                        </ul>
                    </td>
                </tr>
            </table>
        </div>
    </div>
</template>
<script>
export default {
    props: ['data'],
   
}
</script>
<style>
.cv-project{
    border-bottom: orange 2px solid;
    margin-bottom: 5px;
}
.cv-project-info table ul{
    list-style: none;
}
</style>