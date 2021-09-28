<template>
    <div>
        <auto-numeric-input
        :ViewModel="ViewModel"
        ></auto-numeric-input>
        <input v-model="ViewModel"/>:


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
        let ViewModel = ref();
        return{
            ViewModel
        }
    },
};
</script> 
