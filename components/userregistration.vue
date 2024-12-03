<template>
     <v-container align="center">
       <v-card class="text-h2 mt-5 mb-5 pa-10">User Registration</v-card>
    </v-container>
    <v-col cols="12" align="center">
        <v-container>
            <v-text-field
            v-for="(x, index) in USERS"
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

        <v-card>
            <v-table>
                <thead>
                    <tr>
                        <th
                        v-for="(x, index) in TABLE_TITLE"
                        :key="index"
                        >
                          {{ x }}
                        </th> 
                    </tr>
                </thead>
                <tbody>
                    <tr
                    v-for="(x, index) in REGISTER"
                    :key="index"
                    >
                        <td>{{ x.username }}</td>
                        <td>{{ x.password }}</td>
                        <td>{{ x.email }}</td>
                    </tr>
                </tbody>
            </v-table>
        </v-card>
      
    </v-col>


</template>


<script setup>

const USERNAME = ref('')
const PASSWORD = ref('')
const EMAIL = ref('')
const TABLE_TITLE = ref(['USERNAME','PASSWORD', 'EMAIL'])
const REGISTER = ref([])


const USERS = ref([
    {label: 'Username',icon: 'mdi-account', type: 'text', model: USERNAME},
    {label: 'Password', icon: 'mdi-lock', type: 'password', model: PASSWORD},
    {label: 'Email', icon: 'mdi-email', type: 'text', model: EMAIL}
])

const LOGIN_BUTTON = ref([
    {color: 'success', icon: 'mdi-check-bold', text: 'login', margin_right: 'mr-2', route: '/login'},
    {color: 'blue', icon: 'mdi-account-arrow-right', text: 'signup', click: USER_REGISTRATION}
])


function USER_REGISTRATION() {
    if(USERNAME.value && PASSWORD.value && EMAIL.value){
        REGISTER.value.push(
            {username: USERNAME.value, password: PASSWORD.value, email: EMAIL.value}
        )
    USERNAME.value = ''
    PASSWORD.value = ''
    EMAIL.value = ''
    alert('Successfully Registered')
    }
    else {
        alert('Invalid User Input')
    }
}


</script>