<template>
  <div>
    <h2 class="font-weight-light">Contador: {{ contador }}</h2>
    <button class="btn bn--lg btn-danger mr-1" @click="decrementar">-</button>
    <button class="btn bn--lg btn-success" @click="incrementar">+</button>
    <h1>{{ contadorMultiplicado }}</h1>
  </div>
</template>

<script>
import { mapState } from 'vuex';

export default {
  // computed: mapState([ 'contador' ]),
  // computed: {
  // ...mapState([ 'contador' ]),
  // },
  data() {
    return {
    };
    
  },
  computed: {
    ...mapState({
      contador: 'contador',
      alias: 'contador',
      contadorMultiplicado(state) {
        return state.contador * this.contadorLocal; //não pode arrow function
      },
    }),
  },
  methods: {
    decrementar() {
      this.$store.state.contador--;
    },
    incrementar() {
      this.$store.state.contador++;
    },
  },
};
</script>
