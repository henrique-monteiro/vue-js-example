<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <LateralBar />
    </div>
    <div class="column is-three-quarter">
      <Form />
    </div>
  </main>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import LateralBar from './components/LateralBar.vue'
import Form from './components/Form.vue'

export default defineComponent({
  name: 'App',
  components: {
    LateralBar,
    Form
  }

});
</script>
<style>
</style>

