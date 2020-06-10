<template>
    <div>
        <button @click="unwatch">停止监视</button>
    </div>
</template>

<script>
import { ref, watch,reactive } from 'vue'
export default {
    setup(){
        /**
         * 监视单个数据源
         */
        // 1.监视ref数据源
        // const count = ref(1); 

        // watch(count,(newValue,oldValue) => {
        //     console.log(oldValue,newValue);
        // });

        // 2.监视ractive数据源
        /* const state = reactive({count:1});

        // 监视state.count，必须以函数形式定义
        watch(() => state.count,(newValue,oldValue) => {
            console.log(oldValue,newValue);
        }); */

        /**
         * 监视多个数据源
         */
        // const name = ref('tom');
        // const age =ref('18');

        // watch([name,age],([newName,newAge],[oldName,oldAge]) => {
        //     console.log(oldName,newName);
        //     console.log(oldAge,newAge);
        // });

        /**
         * 取消监视
         */
        const count = ref(1);

        // 返回一个用于取消监视的函数
        const unwatch = watch(count,(newValue,oldValue) => {
            console.log(oldValue,newValue);
        })

        setTimeout(() => {
            count.value = 6;
            // state.count = 8;
            // name.value = 'alice';
            // age.value = 16;
        },3000);

        return {
            unwatch
        }
    }
}
</script>