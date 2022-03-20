<template>
  <div class="relative overflow-x-hidden custom-background min-h-screen">
    <NavBar @nav-click="toggleSidebar()" />
    <SideBar :show="showSideBar" />
    <div class="w-full pt-24 transform transition ease-in-out duration-500"
         :class="showSideBar ?'md:pl-60' : 'pl-0'"
    >
      <div class="px-4 md:px-10 py-2">
        <div class="w-full">
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
.custom-background {
  background-repeat: repeat;
}
</style>
<script>
import NavBar from "@/Components/NavBar";
import SideBar from "@/Components/SideBar";
import {defineComponent} from "vue";
import {Head, Link} from "@inertiajs/inertia-vue3";

const sm = 640;
const md = 768;
const lg = 1024;
const xl = 1280;

export default defineComponent({
  components: {
    Head,
    Link,
    NavBar,
    SideBar,
  },
  data() {
    return {
      width: window.innerWidth,
      height: window.innerHeight,
      sm, md, lg, xl,
      showSideBar: false
    }
  },
  created() {
    window.addEventListener("resize", this.onResize);
    let initialWidht = window.innerWidth;
    if (initialWidht < md) {
      this.showSideBar = false;
    }
    if (initialWidht >= md) {
      this.showSideBar = true;
    }
  },
  destroyed() {
    window.removeEventListener("resize", this.onResize);
  },
  methods: {
    toggleSidebar() {
      this.showSideBar = !this.showSideBar;
    },
    onResize(e) {
      this.width = window.innerWidth;
      this.height = window.innerHeight;
      console.log('-----------------');
      console.log(this.width + ',' + this.height);
      console.log('-----------------');
      if (this.width < md) {
        this.showSideBar = false;
      }
      if (this.width > md) {
        this.showSideBar = true;
      }
    },
  },
  computed: {
    backgroundImage() {
      const currentLocation = window.location.href;
      if (currentLocation.includes('allgames') || currentLocation.includes('demo')) {
        return 'http://' + this.$page.props.baseUrl + '/images/background-3.jpeg';
      }
      return 'http://' + this.$page.props.baseUrl + '/images/background-2.jpg';
    },
    backgroundComputedStyle() {
      var style = `background-image : url(${this.backgroundImage});background-size : ${this.width}px;`;
      return style;
    }
  }
})
</script>
