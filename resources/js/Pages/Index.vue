<template>
  <layout>
    <div class="w-full">
      <input type="text"
             class="w-80 text-sm border border-1 border-gray-300 rounded-md focus:outline-none focus:ring-0 focus:border-gray-300">
    </div>
    <div class="w-full flex gap-1 flex-wrap mt-2">
      <button class="flex w-12 h-8 bg-green-200 items-center justify-center relative"
              @click="toggleShowSelectMonth"
      >
        <p class="text-sm text-gray-600">{{ this.selectedMonth != null ? this.selectedMonth.name : '-' }}</p>
        <div v-click-outside="onClickOutside"
             v-if="showMonthList"
             class="absolute bottom-0 left-0 h-8 full translate-y-8 z-20">
          <button @click="selectMonth(month)" class="bg-gray-200 w-12 py-1 hover:bg-gray-300"
                  v-for="(month,index) in months"
                  :key="month">
            <p class="text-sm text-gray-600">{{ month.name }}</p>
          </button>
        </div>
      </button>
      <div v-if="selectedMonth!=null" v-for="(index) in selectedMonth.numberOfDays" :key="index"
           @click="selectDate(index)"
           class="w-8 h-8 border border-gray-300 rounded-md flex justify-center items-center cursor-pointer transition transform ease-in-out duration-200  hover:scale-110"
           :class="index===selectedDate ? 'hover:bg-gray-200 bg-gray-200' :'hover:bg-gray-100'"
      >
        <p class="text-sm text-gray-600">{{ index }}</p>
      </div>
    </div>
    <div class="w-full mt-4">
      <div class="flex flex-wrap gap-4">
        <div @click="test()" v-for="product in products" :key="product.id" class="group relative overflow-hidden">
          <div
            class="w-60 h-40 bg-gray-200 aspect-w-1 aspect-h-1 rounded-md overflow-hidden group-hover:opacity-75 lg:h-80 lg:aspect-none">
            <img :src="product.imageSrc" :alt="product.imageAlt"
                 class="w-full h-full object-center object-cover lg:w-full lg:h-full" />
          </div>
          <div class="mt-4 flex justify-between">
            <div>
              <h3 class="text-sm text-gray-700">
                <a :href="product.href">
                  <span aria-hidden="true" class="absolute inset-0" />
                  {{ product.name }}
                </a>
              </h3>
              <p class="mt-1 text-sm text-gray-500">{{ product.color }}</p>
            </div>
            <p class="text-sm font-medium text-gray-900">{{ product.price }}</p>
          </div>
          <div class="absolute top-0 right-0 h-6 w-6 bg-gray-200 rounded-tr-md">
            <div class="flex h-full w-full justify-center items-center cursor-pointer">
              <p class="text-xs text-gray-500">1</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </layout>
</template>

<style>

</style>

<script>
import {defineComponent} from 'vue'
import {Head, Link} from '@inertiajs/inertia-vue3';
import vClickOutside from "click-outside-vue3"

const products = [
  {
    id: 1,
    name: 'Basic Tee',
    href: '#',
    imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-01.jpg',
    imageAlt: "Front of men's Basic Tee in black.",
    price: '$35',
    color: 'Black',
  },
  {
    id: 1,
    name: 'Basic Tee',
    href: '#',
    imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-01.jpg',
    imageAlt: "Front of men's Basic Tee in black.",
    price: '$35',
    color: 'Black',
  },
  {
    id: 1,
    name: 'Basic Tee',
    href: '#',
    imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-01.jpg',
    imageAlt: "Front of men's Basic Tee in black.",
    price: '$35',
    color: 'Black',
  },
  {
    id: 1,
    name: 'Basic Tee',
    href: '#',
    imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-01.jpg',
    imageAlt: "Front of men's Basic Tee in black.",
    price: '$35',
    color: 'Black',
  },
  {
    id: 1,
    name: 'Basic Tee',
    href: '#',
    imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-01.jpg',
    imageAlt: "Front of men's Basic Tee in black.",
    price: '$35',
    color: 'Black',
  },
];
const months = [
  {
    id: 1,
    name: 'JAN',
    numberOfDays: 31
  },
  {
    id: 2,
    name: 'FEB',
    numberOfDays: 29
  },
  {
    id: 3,
    name: 'MAR',
    numberOfDays: 31
  },
  {
    id: 4,
    name: 'APR',
    numberOfDays: 30
  },
  {
    id: 5,
    name: 'MAY',
    numberOfDays: 31
  },
  {
    id: 6,
    name: 'JUN',
    numberOfDays: 30
  },
  {
    id: 7,
    name: 'JUL',
    numberOfDays: 31
  },
  {
    id: 8,
    name: 'AUG',
    numberOfDays: 31
  },
  {
    id: 9,
    name: 'SEP',
    numberOfDays: 30
  },
  {
    id: 10,
    name: 'OCT',
    numberOfDays: 31
  },
  {
    id: 11,
    name: 'NOV',
    numberOfDays: 30
  },
  {
    id: 12,
    name: 'DEC',
    numberOfDays: 31
  },

]

export default defineComponent({
  components: {
    Head,
    Link,
    vClickOutside
  },
  directives: {
    clickOutside: vClickOutside.directive
  },
  data() {
    return {
      products,
      months,
      selectedDate: null,
      selectedMonth: null,
      showMonthList: false
    }
  },
  methods: {
    onClickOutside(event) {
      this.showMonthList = false;
    },
    selectMonth(month) {
      this.selectedMonth = month;
    },
    toggleShowSelectMonth() {
      this.showMonthList = !this.showMonthList;
    },
    test() {
      console.log('-----------------');
      console.log('sdfdsfdh');
      console.log('-----------------');
    },
    selectDate(index) {
      console.log('-----------------');
      console.log(index);
      console.log('-----------------');
      this.selectedDate = index;
    }
  }
})
</script>
