<template>
  <layout>
    sdfhdsjkfhdhfds
  </layout>
</template>

<style>

</style>

<script>
import {defineComponent} from 'vue'
import {Head, Link} from '@inertiajs/inertia-vue3';
import Layout from "@/Layouts/Layout";

export default defineComponent({
  components: {
    Head,
    Link,
    Layout
  },
  props: {
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
  }
})
</script>
