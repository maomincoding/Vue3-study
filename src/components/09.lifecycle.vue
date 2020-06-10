<template>
    <div>
        <p>{{ count }}</p>
        <button @click="count++">修改count</button>
    </div>
</template>

<script>
import { onBeforeMount, onMounted,onBeforeUpdate,onUpdated,onBeforeUnmount, onUnmounted, ref } from 'vue'
export default {
    setup(){
        onBeforeMount(() => {
            console.log('onBeforeMount');
        })
        onMounted(() => {
            console.log('onMounted');
        })
        onBeforeUpdate(() => {
            console.log('onBeforeUpdate');
        })
        onUpdated(() => {
            console.log('onUpdated');
        })
        onBeforeUnmount(() => {
            console.log('onBeforeUnmounted');
        })
        onUnmounted(() => {
            console.log('onUnmounted');
        })

        const count =ref(1);

        return {
            count
        }
    },
    // 向下兼容 Vue 2.x
    mounted(){
        console.log('Vue 2.x-----mounted');
    }
}
</script>