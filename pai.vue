<template>
    <div>
        
        <label for="">pai</label>
        <input type="number" v-model="ViewModel"/>
        <br>
          <label for="">filho</label>
        <auto-numeric-input
        :ViewModel="ViewModel"
        @teste="funcao"
       
        ></auto-numeric-input>



    </div>
</template>
 
<script>
import AutoNumericInput from "./AutoNumericInput.vue"
import { ref } from "vue";
export default {
    components:{
        AutoNumericInput
    },
    setup() {
        let ViewModel = ref(0);
        const funcao = (e) =>{
            console.log("atiualiza vw", e)
            ViewModel.value = e;
        }
        return{
            ViewModel,
            funcao
        }
    },
};
</script> 
