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
/// outro ex com reatividade pai para filho e filho para pai com marcara monetaria no input
<template>
    <money3 v-model="valueInput" v-bind="config"></money3> {{ ViewModel }}
</template>

<script>
import { Money3Component } from "v-money3";
import { watch, ref } from "vue";

export default {
    components: { money3: Money3Component },
    props: {
        ViewModel: {
            type: [String, Number],
            required: false,
            default: 0,
        },
    },
    emits: ["teste"],
    setup(props, context) {
        let valueInput = ref(0);

        watch(props, () => {
            valueInput.value = props.ViewModel;
        });
        watch(valueInput, () => {
            context.emit("teste", valueInput.value);
        });
        return {
            valueInput,
            amount: "12345.67",
            config: {
                masked: false,
                prefix: "$",
                suffix: "",
                thousands: ",",
                decimal: ".",
                precision: 2,
                disableNegative: false,
                disabled: false,
                min: null,
                max: null,
                allowBlank: false,
                minimumNumberOfCharacters: 0,
            },
        };
    },
};
</script>
