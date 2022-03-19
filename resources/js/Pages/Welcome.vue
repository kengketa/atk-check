<template>
  <div class="bg-gray-200 min-h-screen">
    <div class="w-full h-screen flex items-center justify-center">
      <p class="text-xl text-green-800 font-bold">ATK CHECK TEST SYSTEM</p>
    </div>
  </div>
</template>

<style>

</style>

<script>
import {defineComponent} from 'vue'
import {Head, Link} from '@inertiajs/inertia-vue3';

export default defineComponent({
  components: {
    Head,
    Link,
  },
  props: {
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
  }
})
</script>
