<template>
        <div class="card">
            <h1>Perguntas frequentes</h1>
            <small>Escolha a categoria desejada</small>
            <ul class="lista">
                <li @click="currentView = 'CardCategory'"></li>
                <li @click="currentView = 'CardQuestion'"></li>
                <li @click="currentView = 'CardAnswer'"></li>
            </ul>
            <component :is="currentView"></component>
        </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
   
    
})
</script>

<style scoped>
   
    .card {
        border-radius: 15px;
        background-color: #232323;
        color: #fff;
        display: grid;
        justify-content: center;
        align-content: center;
        justify-items: center;
        align-items: center;
    }
</style>