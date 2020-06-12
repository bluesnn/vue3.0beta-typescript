<template>
  <div>
    <HelloWorld :message="message"/>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue';
import HelloWorld  from '@/components/HelloWorld.vue'

export default defineComponent({
  components: {
    HelloWorld
  },

  setup() {
    return reactive({
      message: 'hi'
    })
  }
})
</script>
