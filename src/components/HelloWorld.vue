<template>
  <div class="hello">
    <h1>{{ message }}</h1>
    <div>{{ state.msg }}</div>
    <div>{{ state.num }}</div>
    <button @click="double">add</button>
    <div>{{ count }}</div>
    <button @click="increment">increment</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, computed, ComputedRef } from 'vue';

interface stateInterface {
  msg: string;
  num: number;
}

export default defineComponent({
  props: {
    message: {
      type: String
    }
  },

  setup(props) {
    console.log(props.message)
    const state: stateInterface = reactive<stateInterface>({
      msg: 'zheshiyiduanhua',
      num: 0
    });
    const count: any = ref(0)

    const double: ComputedRef<number> = computed<number>(() => state.num * 2)

    function increment (): void {
      count.value++
    }

    return {
      state,
      count,
      double,
      increment
    }
  }
})
</script>

<style scoped lang="scss">

</style>
