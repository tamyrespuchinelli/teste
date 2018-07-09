<template>
  <div class="hello">
    
    <b-container>
       <b-row>
         <b-table striped hover :items="items" :fields ="fields"/>
       </b-row>
      <b-row>
        <b-col cols="12" lg="6">
        <b-form-group id="title-group"
                    label="Titulo:"
                    label-for="title"
                    >
        <b-form-input id="title"
                      type="text"
                      v-model="form.title"
                      placeholder="titulo">
        </b-form-input> 
      </b-form-group></b-col>
        <b-col cols="12" lg="6"> 
        <b-form-group id="content-group"
                    label="Conteúdo:"
                    label-for="content"
                   >
        <b-form-input id="title"
                      type="text"
                      v-model="form.content"
                      placeholder="contéudo">
        </b-form-input>
      </b-form-group></b-col>
        
      </b-row>
      <b-col>
        <div class ="float-right">
          <b-button @click="addItem">ok </b-button>
      </b-col>
    </b-container>  
  </div>
</template>

<script>
import {required} from 'vuelidate/libs/validators';
export default {
  name: 'HelloWorld',
  data () {
    return {
      form:{
        title:"",
        content:""

      },
      items:[]
    }
  },
  methods:{
    addItem(){
      this.items.push({...this.form});
      this.form.title ="";
      this.form.content ="";
    }
  },
  validations: {
    form:{
      title:{
        required
        },
        content:{
          required

        }
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
