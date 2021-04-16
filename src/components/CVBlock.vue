<template>
    <div class="cv-block">
         <h3 class="title">{{data.Title}}</h3>
        <div class="content" v-if="data.Type==1">
            <table>
                <tr v-for="(value, key) in data.Item" :key="key">
                    <td style="font-weight:700">{{key}}</td>
                    <td style="font-weight:500">: {{value}}</td>
                </tr>
            </table>
        </div>
        <div class="content" v-else>
            <ul>
                <li v-for="(value, key) in data.Item" :key="key"> {{value}} </li>
            </ul>
        </div>

    </div>
</template>
<script>
export default {
    props: ['data'],
   
}
</script>