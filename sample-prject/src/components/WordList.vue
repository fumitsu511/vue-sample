<script setup lang="ts">
import { ref } from 'vue'
import axios from 'axios'
import router from '@/router'


const datas =
    [
        { title1: "r1-d1", title2: "r1-d2", title3: "r1-d3", title4: "r1-d4", title5: "r1-d5", },
        { title1: "r2-d1", title2: "r2-d2", title3: "r2-d3", title4: "r2-d4", title5: "r2-d5", },
        { title1: "r3-d1", title2: "r3-d2", title3: "r3-d3", title4: "r3-d4", title5: "r3-d5", },
    ]



</script>

<template>
    <div class="container">
        <h1>title</h1>
        <table class="main-table" border="0">
            <thead>
                <tr>
                    <th>タイトル１</th>
                    <th>タイトル２</th>
                    <th>タイトル３</th>
                    <th>タイトル４</th>
                    <th>タイトル５</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="data in datas" :key="data.title1">
                    <td class="-left">{{ data.title1 }}</td>
                    <td class="-left">{{ data.title2 }}</td>
                    <td class="-right">{{ data.title3 }}</td>
                    <td class="-left">{{ data.title4 }}</td>
                    <td class="-right">{{ data.title5 }}</td>
                </tr>
            </tbody>
        </table>

    </div>
</template>

<style scoped>

.main-table{
table-layout: auto;
width: 100%;
font-size: 16px;
}

.main-table thead th {
    background: #28d;
    font-weight: bold;
    color: #fff;
    padding-top: 12px;
    padding-bottom: 12px;
}

.main-table tbody td {
    background: #f9f9f9;
    padding-left: 24px;
    padding-right: 24px;
}



.main-table tbody tr:nth-child(2n) td {
    background: #ececec;
}

.main-table tbody tr:hover td {
    background-color: #cfebf3;

}

.-right{
    text-align: right;
}

.-left{
    text-align: left;
}

</style>
