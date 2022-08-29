<template>
        <div class="card">
            <img src="../assets/images/astronaut.svg" alt="" srcset="">
            <div>   
                <h1 class="headerMain">Perguntas frequentes</h1>
                <small>Escolha a categoria desejada</small>
            </div>
            <div>
                <ul class="lista">  
                    <li class="item" v-for="category in faqCategories" :key="category.id"><img class="iconeImg" src="../assets/images/rocket.svg"/><span class="textCategory">{{ category.title}}</span></li>
                </ul>
            </div>
        </div>
        <transition>
        </transition>
</template>

<script lang="ts">

import { defineComponent } from 'vue'

export default defineComponent({
        data() {
            return {
                faqCategories: null,
                icons: [],
                images: ['rocket.svg','astronaut-helmet.svg','student-hat.svg','partnership.svg'],
            }
        },
        methods: {
            async getCategories(){
                const req = await fetch("http://localhost:3000/faqCategories")
                const data = await req.json();
                console.log(this.icons)
                console.log(data);
                this.faqCategories = data;
            }     
        },
        created(){
            this.getCategories();
        }
}) 
</script>

<style scoped>
    ul.lista {
        padding: 0;
    }
    .headerMain {
        margin: 0;
    }
    .textCategory {
        font-size: 20px;
        font-weight: 500;

    }
    .iconeImg {
        width: 40px;
        height: 40px;
    }
    .item {
        display: grid;
        grid-template-columns: 1fr 1fr;
        justify-items: center;
        align-items: center;
    }
   .lista {
    list-style: none;
    display: grid;
    grid-auto-flow:row;
   }
    .card {
        border-radius: 15px;
        background-color: #232323;
        color: #fff;
        display: grid;
        grid-row-gap: 1rem;
        justify-items: start;
        justify-content: space-around;
    }

    /* transições */
    .v-enter-from, .v-leave-to {
        opacity: 0;
    }

    .v-enter-active, .v-leave-active {
        transition: opacity .5s;
    }
</style>