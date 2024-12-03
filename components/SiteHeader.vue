<template>
    <v-col cols="12" height="400" class="bg-blue-darken-1">
        <v-row justify="end" class="--red pa-5 d-flex flex-row"> 
            <v-row class="--red" justify="end">
                <v-row justify="start">
                    <div class="text-h2">Sourcehero</div>
                </v-row>
                <v-list-item link title="List Item 1"></v-list-item>
                <v-list-item link title="List Item 2"></v-list-item>
                <v-list-item link title="List Item 3"></v-list-item>
                <v-btn 
                v-for="(x, index) in buttons"
                :key="index"
                :class="x.space"
                :text="x.title"
                :color="x.color"
                >
                </v-btn>
            </v-row>
        </v-row>
    </v-col>
</template>

<style scoped>

/* 
.--red {
    border: 1px solid red;
}
*/
</style>


<script setup>

const buttons = ref([
    { title: 'login', space: 'mr-5', color: 'green'},
    { title: 'signup', space: 'mr-5', color: 'blue'},
    
])

</script>