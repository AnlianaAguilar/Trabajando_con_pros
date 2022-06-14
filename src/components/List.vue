<template> <!---->
  <div class="form">
    <h1 class="form-content" >Tarea</h1>
    <input class="form-content" type="text" v-model="task" placeholder="Ingrese nueva tarea"> <!-- se coloca v-model para sincronizar el contenido la variable (task) con el contenido que tenga un elemento HTML-->
    <button class="form-content" @click="add">Añadir</button> <!--se añade evento y llama el metodo a usar-->
  </div>
  <div>
    <my-list-tasks :tasks="tasks" @deleteTask='eliminate'/>
    </div>
</template>

<script>
import List_task from '@/components/List_task.vue'
export default {
  name: 'list-comp',
  // props: {},
  data: function(){
    return {    // se crean las varibles
      task:"",
      tasks:[]
    }
  },
  // computed: {},
  methods: {
    add:function(){ // se crea evento para añadir cada task en un array
      if(this.task==""){
        alert("Debe agregar una tarea")
      }
      else{
        this.tasks.push(this.task)
        this.task="" //dejar en blanco el campo
      }  
    },
    eliminate(event){  // se crea metodo
      this.tasks.splice(event,1)
    }
  },
  // watch: {},
  components: {
    'my-list-tasks':List_task
  },
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
}
</script>

<style scoped>

.form{
  display: flex;
  justify-content: center;  
}

.form-content{
  margin: 0 10px;

}

input{
  width: 250px;
  color: grey;
  font-size: 15px;
}

button{
  font-size:15px ;
  background: rgb(223, 220, 220);
  border-radius: 5px;
}  
</style>
