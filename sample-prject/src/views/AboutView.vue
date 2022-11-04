<script setup lang="ts">
import { ref } from 'vue'

const datas = ref();
datas.value =
    [
        { title1: "r1-d1", title2: "r1-d2" , title3: 100},
        { title1: "r2-d1", title2: "r2-d2" , title3: 200},
        { title1: "r3-d1", title2: "r3-d2" , title3: 300},
    ]
</script>

<template>
  <main>
    <div class="container">
      <h1>title</h1>
      <div class="box">
        <div class="row" v-for="data in datas" :key="data.title1">
          <label class="row-label">{{data.title1}}</label>
          <label class="row-label">{{data.title2}}</label>
          <input type="text" class="row-text" v-model="data.title3" />
        </div>
        <div class="submit-group">
                    <button class="submit-button">登録する</button>
                </div>
      </div>
      
    </div>
  </main>
</template>

<style scoped>

.box{
  background: #ebebeb;
  padding: 12px;
}
 .row{
  display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    padding: 8px;

 }

 .row-text {
  box-sizing: border-box;
  display: block;
  width: 100%;
  border-width: 1px;
  border-style: solid;
  padding: 4px;
  outline: 0;
  font-family: inherit;
  font-size: 0.95em;
  background: #fff;
  border-color: #bbb;
  color: #555;
}

.row-text:focus{
  border-color: #888;
}
</style>
