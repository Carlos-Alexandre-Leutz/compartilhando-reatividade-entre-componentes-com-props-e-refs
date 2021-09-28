<template>
    {{ ViewModel }}
</template>

<script>
import { watch } from "vue";

export default {
  
    props: {
        ViewModel: {
            type: [String],
            required: false,
            default: "",
        },
    },
    setup(props) {
        console.log("vMOdel", props.ViewModel);
        
        watch(props, () => {
            console.log("vMOdel mudou", props.ViewModel);
        });
    },

};
</script>
