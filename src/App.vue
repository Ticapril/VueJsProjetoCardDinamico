<template>
  <div>
    <ul class="lista">
      <li @click="currentView = 'CardCategory'">Categorias</li>
      <li @click="currentView = 'CardQuestion'">Perguntas</li>
      <li @click="currentView = 'CardAnswer'">Respostas</li>
    </ul>
    <component :is="currentView"></component>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CardAnswer   from "./pages/CardAnswer.vue";
import CardCategory from "./pages/CardCategory.vue";
import CardQuestion from "./pages/CardQuestion.vue";

export default defineComponent({
  components: {
    CardAnswer,
    CardCategory,
    CardQuestion,
  },
  data() {
    return {
      currentView: "CardCategory",
    };
  },
});
</script>

<style>
div#app {
  background-color: rgba(255, 255, 255, 0.6);
}
</style>
