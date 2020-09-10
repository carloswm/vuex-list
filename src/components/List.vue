<template>
  <div class="container">
    <ul class="list-group">
      <li  v-for="(item, index) of arrayOrdenado" :key="item" @click="aumentar(index)"
      class="list-group-item d-flex justify-content-between align-items-center">
        {{item.nombre}}
        <span class="badge badge-primary badge-pill">{{item.cantidad}}</span>
      </li>
    </ul>
    <button type="button" class="btn btn-danger btn-lg btn-block" @click="reset">Reiniciar</button> 
  </div>
</template>

<script>

import {mapState, mapMutations} from 'vuex';

export default {
    name: 'List',
    computed: {
      ...mapState(['frutas']),
      arrayOrdenado(state) {
        let orden = (a,b) => b.cantidad - a.cantidad;
        return state.frutas.sort(orden);
      }
    },
    methods: {
      ...mapMutations(['aumentar','reset'])
    }
}
</script>