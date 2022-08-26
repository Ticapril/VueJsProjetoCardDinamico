<template>
    <CardCategory />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CardCategory from './components/CardCategory.vue';

export default defineComponent({
  name: 'App',
  components: {
    CardCategory
  }
});
</script>

<style>
    div#app {
        background-color: rgba(255, 255, 255, .6);
    }
</style>
