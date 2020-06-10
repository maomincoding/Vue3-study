<template>
    <div>
        
    </div>
</template>

<script>
import { readonly, reactive } from 'vue'
export default {
    setup(){
        const state = reactive({ count: 1});
        const proxy = readonly(state);
        console.log(state.count);
        console.log(proxy.count);

        // 代理对象只读的，不允许修改
        // proxy.count++;

        // 修改原始对象时代理对象也会响应式变化 
        state.count++;
        console.log(state.count);
        console.log(proxy.count);

    }
}
</script>