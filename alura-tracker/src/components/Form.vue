<template>
  <div class="box">
    <div class="columns">
      <div
          class="column is-8"
          role="form"
          aria-label="Formulário para criação de uma nova tarefa"
      >
        <input
            type="text"
            class="input"
            placeholder="Qual tarefa você deseja iniciar?"
        />
      </div>
      <div class="column">
        <div
            class="is-flex is-align-items-center is-justify-content-space-between"
        >
          <section>
            <strong>
              {{ elapsedTime }}
            </strong>
          </section>
          <button class="button" @click="begin">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="end">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "Form",

  //data () é um método que retorna objetos com informações pertinentes para este componente (aparentemente é a ideia de variáveis globais)
  data () {
    return {
      timeInSeconds: 0,
      stopwatch: 0
    }
  },

  // computed é acionado conforme uma informação é alterada. elapsedTime é uma propriedade de computed
  computed: {
    elapsedTime () : string {
      return new Date(this.timeInSeconds * 1000).toISOString().substr(11,8)
    }
  },

  methods: {
    begin () {
      // começar a contagem
      // 1 seg = 1000 ms
      this.stopwatch = setInterval(() => {
        this.timeInSeconds += 1
      }, 1000)
    },
    end () {
      clearInterval(this.stopwatch)
    }
  }
});
</script>