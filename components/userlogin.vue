<template>
    <v-container align="center">
       <v-card class="text-h2 mt-5 mb-5 pa-10">User Login</v-card>
    </v-container>
    <v-col cols="12" align="center">
        <v-container>
            <v-text-field
            v-for="(x, index) in USER_LOGIN"
            :key="index"
            :label="x.label"
            :type="x.type"
            :prepend-inner-icon="x.icon"
            v-model="x.model"
            >
            </v-text-field>

            <v-btn
            v-for="(x, index) in LOGIN_BUTTON"
            :key="index"
            :text="x.text"
            :color="x.color"
            :prepend-icon="x.icon"
            :class="x.margin_right"
            :to="x.route"
            @click="x.click"
            >
            </v-btn>
        </v-container>
      
    </v-col>

</template>


<script setup>

const USERNAME = ref('')
const PASSWORD = ref('')

const USER_LOGIN = ref([
    {label: 'Username',icon: 'mdi-account', type: 'text', model: USERNAME},
    {label: 'Password', icon: 'mdi-lock', type: 'password', model: PASSWORD}
])

const LOGIN_BUTTON = ref([
    {color: 'success', icon: 'mdi-check-bold', text: 'login', margin_right: 'mr-2', click: USER_AUTH},
    {color: 'blue', icon: 'mdi-account-arrow-right', text: 'signup', route: '/signup'}
])


function USER_AUTH() {
    if(USERNAME.value === '1' && PASSWORD.value === '1'){
        alert('Login Successfull')
    }
    else {
        alert('Login Failed')
    }
}

</script>