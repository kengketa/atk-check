<template>
  <nav
    class="z-100 bg-gray-200 fixed top-0 w-full h-20 flex justify-between items-center px-4">
    <div class="flex w-48 justify-left">
      <button class="button" @click="$emit('navClick')">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
    </div>
  </nav>
</template>

<script>
import {defineComponent} from 'vue'
import {Link} from '@inertiajs/inertia-vue3';


export default defineComponent({
  name: "HeadNavBar",
  components: {
    Link,
  },
  mounted() {

  },
  data() {
    return {
      showOptionCard: false,
      showProfileModal: false,
      alert: {
        show: false,
        title: "",
        subTitle: "",
        icon: ""
      }
    }
  },
  methods: {
    onClickOutsideMenuOption(event) {
      this.showOptionCard = false;
    },
    updatedProfile() {
      this.alert.title = "อัพเดท profile";
      this.alert.subTitle = `อัพเดท profileสำเร็จ`;
      this.alert.icon = "images/deposit_icon.png";
      this.alert.show = true;
    }
  }
})
</script>
<style>
.z-100 {
  z-index: 80;
}
</style>
