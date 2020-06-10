<template>
    <div>
        <h3 ref="h3Ref">跟汤哥学前端，走上人生巅峰</h3>
        <hr>
        <comp-ref ref="compRef"></comp-ref>
    </div>
</template>

<script>
import CompRef from './13.compRef'
import { ref,onMounted } from 'vue'
export default {
    setup(){
        /**
         * 获取元素
         */
        // 创建一个值为null的ref对象，并返回
        const h3Ref = ref(null);

        /**
         * 获取组件
         */
        const compRef = ref(null); 

        // 在页面渲染完成后才能获取到对应的元素
        onMounted(() => {
            // console.log(h3Ref.value); // DOM对象
            // h3Ref.value.style.color='red';

            console.log(compRef.value); // 子组件
            console.log(compRef.value.msg);
            compRef.value.change(); // 面试题：父组件如何调用子组件的方法
        });

        return {
            h3Ref,
            compRef
        }
    },
    components:{
        'comp-ref':CompRef
    }
}
</script>