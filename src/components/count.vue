<template>
    <div>
        <h3>{{title}}</h3>
        <p>支持数{{supN}}</p>
        <p>反对数{{oppN}}</p>
        <p>vue使用率{{result}}</p>
        <button @click="change(0)">支持</button>
        <button @click="change(1)">反对</button>
    </div>
</template>
<script>
import { watchEffect, ref, reactive, toRefs, computed } from 'vue';
export default {
    props: {
        title: String
    },
    // 相当于放弃data，methods等，全都放在setup里
    setup(props) {
        console.log(props);

        // computed的get与set
        let result = computed({
            get:() => {
                let total = state.supN + state.oppN;
                return total ===0 ? '--' : ((state.supN / total) * 100).toFixed(2) + '%';
            },
            set: val => {
                console.log(val);
            }
        });
        let state = reactive({
            supN: 0,
            oppN: 0
        });
        function change(val) {
            val === 0 ? state.supN++ : state.oppN++;
            result.value = 23;
        };
        return {
            ...toRefs(state),
            change,
            result
        };   
    }
}
</script>