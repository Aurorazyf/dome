<template>
 今年的年纪：<input type="text" v-model="age"><br>
 明年的年纪：<input type="text" v-model="nextAge">
</template>

<script>
import { computed, ref } from 'vue'
export default {
  name: 'App',
  setup() {
    const age = ref(18)

    // 计算属性第一种写法
    // const nextAge = computed(() => {
    //   return +age.value + 1
    // })

    // 计算属性第二种写法
    const nextAge = computed({
      get() {
        return +age.value + 1
      },
      set(val) {
        age.value = val - 1
      }
    })
    return {
      age,
      nextAge
    }
  }
}
</script>
