<script setup>
import { computed } from 'vue'
import { useStore } from 'vuex'
import TheWelcome from '@/components/TheWelcome.vue'

const store = useStore();
const count = computed(() => store.getters.getCounter);

const countHandler = () => {
  store.dispatch("increment",1);
};
</script>

<template>
  <main>
    <TheWelcome />
    <div class="container">
      <h3>Count : {{ count }}</h3>
      <button @click="countHandler">Count Handler</button>
    </div>
  </main>
</template>

<style scoped>
.container{
  margin-left: 6rem;
}

h3 {
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
  color: var(--color-heading);
}

button{
  background-color: var(--color-heading);
  color: white;
  padding: .75rem;
  border: none;
}
</style>