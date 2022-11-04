<script setup lang="ts">
import { ref } from 'vue'
import axios from 'axios'
import router from '@/router'

const content = ref<string>("")
const userId = ref<string>("")
const password = ref<string>("")

const PushLogin = () => {
    axios.get("https://umayadia-apisample.azurewebsites.net/api/management")
        .then(response => {
            content.value = response.data
        })

    console.log("userId: " + userId.value)
    console.log("password: " + password.value)

    if (userId.value !== "" && password.value !== "") {
        router.push({ path: "/" })
    }


}




</script>

<template>
    <div class="container">
        <h1>title</h1>
        <div class="box">
            <!-- <h1 class="login-header">Login</h1> -->
            <div class="login-container">
                <div class="input-group">
                    <label class="input-label" for="userId">ユーザーID</label>
                    <input type="text" class="input-text" id="userId" v-model="userId" />
                </div>

                <div class="input-group">
                    <label class="input-label" for="password">パスワード</label>
                    <input type="password" class="input-text" id="password" v-model="password" />
                </div>

                <div class="submit-group">
                    <button class="submit-button" @click="PushLogin()">ログイン</button>
                </div>
                <div> <span>{{ content }} </span></div>
            </div>
        </div>


    </div>
</template>

<style scoped>

</style>
