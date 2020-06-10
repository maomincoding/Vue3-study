<template>
    <div>
        <p>{{ count }}</p>
        <p>{{ age }}</p>

        <button @click="change">修改age</button>
    </div>
</template>

<script>
import { ref, isRef, reactive, isReactive, readonly, isReadonly, isProxy, unref, toRef, toRefs } from 'vue'
export default {
    setup(){
        /**
         * isRef
         */
        const count = ref(1);
        // console.log(isRef(count));
        // console.log(isRef(123));
        // console.log(isRef(count) ? count.value : count);

        /**
         * isReactive
         */
        const state = reactive({
            name:'tom',
            age:18
        }) 
        // console.log(isReactive(state));

        /**
         * isReadonly
         */
        const obj = readonly(state); 
        // console.log(isReadonly(obj));

        /**
         * isProxy
         */
        // console.log(isProxy(count)); 
        // console.log(isProxy(state)); 
        // console.log(isProxy(obj)); 

        /**
         * unref
         */
        // console.log(unref(count)); 

        /**
         * toRef
         */
       /*  const ageRef = toRef(state,'age');   // reference 引用
        // ageRef.value++;
        state.age++;

        console.log(state.age);
        console.log(ageRef.value); */

        /**
         * toRefs
         */
        /* const stateRef = toRefs(state);
        // state.age++;
        stateRef.age.value++;

        console.log(state.age);
        console.log(stateRef.age.value); */

        const change = () => {
            state.age++;
        }

        return {
            count,
            // ...state, // ES6展开运算符
            ...toRefs(state), // 使用秋Refs转换，此时具有响应式
            change
        }
    }
}
</script>