<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <LateralBar />
    </div>
  </main>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import LateralBar from './components/LateralBar.vue'

export default defineComponent({
  name: 'App',
  components: {
    LateralBar
  }

});
</script>
<style>
</style>

