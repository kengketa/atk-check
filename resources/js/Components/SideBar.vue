<template>
  <nav
    class="z-100 bg-gray-300 w-60 h-screen fixed left-0 top-20 px-4 transition translate ease-in-out overflow-y-auto scrollbar-hide"
    :class="computedSideBar"
  >
    <div class="grid grid-cols-1 gap-2 mt-10 mb-28">
      <Link>sdfdsfhsdj</Link>
      <Link>sdfdsfhsdj</Link>
      <Link>sdfdsfhsdj</Link>
      <Link>sdfdsfhsdj</Link>
    </div>
  </nav>
</template>

<script>
import {defineComponent} from 'vue'
import {Link} from '@inertiajs/inertia-vue3';

export default defineComponent({
  name: "SideBar",
  components: {
    Link,
  },
  props: {
    show: {
      type: Boolean,
      required: true
    },
  },
  data() {
    return {
      demoMode: false
    }
  },
  mounted() {
    const url = window.location.href;
    if (url.includes('demo')) {
      this.demoMode = true;
    }
  },
  methods: {
    isUrl(...urls) {
      return urls.some((url) => route().current(url));
    },
  },
  computed: {
    computedSideBar() {
      if (this.show === true) {
        return 'translate-x-0';
      }
      if (this.show === false) {
        return '-translate-x-60'
      }
      //return '-translate-x-60 md:-translate-x-0'
    },
  }
})
</script>
<style>
.z-100 {
  z-index: 80;
}
</style>
