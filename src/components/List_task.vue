<template><!---->
  <div>
    
    <ul v-for="(task, index) in tasks" :key="index"> <!--se crea un for que recorra el array-->
      <li>
        {{task}}
        <button @click="eliminate(index)">Eliminar</button> <!--se llama evento pasando el parametro a eliminar-->
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'List-tasks',
  props: { // se crea el dato que recibe el padre
    tasks:{
      type:Array,
      require: true
    }
  },
  data: function(){
    return {}
  },
  // computed: {},
  methods: { //se crea metodo
    eliminate(index){
      this.$emit('deleteTask',index)
    }
  },
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
}
</script>

<style scoped>

ul{
  display: flex;
  margin-left:45%;
}
  
</style>

