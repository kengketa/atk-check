<template>
  <layout>
    <label for="price" class="block text-sm font-medium text-gray-700 mt-4">ค้นหา </label>
    <div>
  <div class="mt-4 relative rounded-md">
    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
    </div>
    <input type="text" name="price" id="price" class="focus:ring-indigo-500 focus:border-indigo-500 block w-1/3 pl-7 pr-12 sm:text-sm  rounded-md" ค้นหา="">
  </div>
</div>
<div class="bg-white px-4 py-3 flex items-center justify-between border-gray-200 sm:px-6">
  <div class="flex-1 flex justify-between sm:hidden">
    <a href="#" class="relative inline-flex items-center px-4 py-2 border border-gray-300 text-sm font-medium rounded-md text-gray-700 bg-white hover:bg-gray-50"> Previous </a>
    <a href="#" class="ml-3 relative inline-flex items-center px-4 py-2 border border-gray-300 text-sm font-medium rounded-md text-gray-700 bg-white hover:bg-gray-50"> Next </a>
  </div>
  <div class="hidden sm:flex-1 sm:flex sm:justify-between mt-6">
   <div class="static ...">
    <div class="relative"> 
      <div
        @click="toggleShow()"
        class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
        rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500 transition duration-500 transform ease-in-out hover:scale-90 hover:text-white">
        <p>{{ selectedMonth }}</p>
      </div>
      <div v-if="showMonthList" class="absolute top-10 z-50" id="month-group"> 
        <div
          @click="selectMonth(null)"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>None</p>
        </div>
        <div
          @click="selectMonth('Jan')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>Jan</p>
        </div>
        <div
          @click="selectMonth('Feb')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>Feb</p>
        </div>
         <div
          @click="selectMonth('Mar')"
            class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
            rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
            <p>Mar</p>
        </div>
        <div
          @click="selectMonth('Apr')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
            rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
            <p>Apr</p>
        </div>
        <div
          @click="selectMonth('May')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>May</p>
        </div>
        <div
          @click="selectMonth('Jun')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>Jun</p>
        </div>
        <div
          @click="selectMonth('Jul')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>Jul</p>
        </div>
        <div
          @click="selectMonth('Aug')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>Aug</p>
        </div>
        <div
          @click="selectMonth('Sep')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>Sep</p>
        </div>
        <div
          @click="selectMonth('Nov')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>Nov</p>
        </div>
        <div
          @click="selectMonth('Dec')"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>Dec</p>
        </div>
      </div>
    </div>
    </div>
    
      <div> 
      <nav class="relative z-0 inline-flex rounded-md shadow-sm -space-x-px" aria-label="Pagination">

        <!-- Current: "z-10 bg-indigo-50 border-indigo-500 text-indigo-600", Default: "bg-white border-gray-300 text-gray-500 hover:bg-gray-50" -->
        <a href="#" aria-current="page" class="rounded-md z-10 bg-indigo-50 border-indigo-500 text-indigo-600 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 1 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 2 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 3 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 4 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 5 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 6 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 7  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 8  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 9 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 10 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 11 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 12 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 13 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 14  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 15  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 16 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 17 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 18 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 19 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 20 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 21  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 22  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 23 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 24 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 25 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-3.5 py-2 border text-sm font-medium"> 26 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 27 </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 28  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 29  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 30  </a>
        <a href="#" class="rounded-md bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-3.5 py-2 border text-sm font-medium"> 31  </a>
      </nav>
    </div>


  </div>
</div>
      <h2 class="text-2xl font-extrabold text-gray-900 mt-8">atkcheck</h2>

      <div class="mt-6 space-y-12 lg:space-y-0 lg:grid lg:grid-cols-3 lg:gap-x-6">
        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://static.thairath.co.th/media/dFQROr7oWzulq5Fa3yfpiTfzr23tpMkmn4TSR8iD4VHX2k49sq9uzGz521udlD8119i.jpg">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่1
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย ววววววว นนนนน</p>
        </div>

        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://media.timeout.com/images/105853179/image.jpg" alt="Wood table with porcelain mug, leather journal, brass pen, leather key ring, and a houseplant." class="w-full h-full object-center object-cover">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่2
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย รรรรรรร พพพพพพ</p>
        </div>

        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg" alt="Collection of four insulated travel bottles on wooden shelf." class="w-full h-full object-center object-cover">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่3
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย aaaaaaa  </p>
        </div>
      </div>
<div class="mt-6 space-y-12 lg:space-y-0 lg:grid lg:grid-cols-3 lg:gap-x-6">
        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://static.thairath.co.th/media/dFQROr7oWzulq5Fa3yfpiTfzr23tpMkmn4TSR8iD4VHX2k49sq9uzGz521udlD8119i.jpg">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่1
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย ววววววว นนนนน</p>
        </div>

        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://media.timeout.com/images/105853179/image.jpg" alt="Wood table with porcelain mug, leather journal, brass pen, leather key ring, and a houseplant." class="w-full h-full object-center object-cover">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่2
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย รรรรรรร พพพพพพ</p>
        </div>

        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg" alt="Collection of four insulated travel bottles on wooden shelf." class="w-full h-full object-center object-cover">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่3
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย aaaaaaa  </p>
        </div>
      </div>
      <div class="mt-6 space-y-12 lg:space-y-0 lg:grid lg:grid-cols-3 lg:gap-x-6">
        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://static.thairath.co.th/media/dFQROr7oWzulq5Fa3yfpiTfzr23tpMkmn4TSR8iD4VHX2k49sq9uzGz521udlD8119i.jpg">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่1
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย ววววววว นนนนน</p>
        </div>

        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://media.timeout.com/images/105853179/image.jpg" alt="Wood table with porcelain mug, leather journal, brass pen, leather key ring, and a houseplant." class="w-full h-full object-center object-cover">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่2
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย รรรรรรร พพพพพพ</p>
        </div>

        <div class="group relative">
          <div class="relative w-full h-80 bg-white rounded-lg overflow-hidden group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
            <img src="https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg" alt="Collection of four insulated travel bottles on wooden shelf." class="w-full h-full object-center object-cover">
          </div>
          <h3 class="mt-6 text-sm text-gray-500">
            <a href="#">
              <span class="absolute inset-0"></span>
              นักเรียนคนที่3
            </a>
          </h3>
          <p class="text-base font-semibold text-gray-900">นาย aaaaaaa  </p>
        </div>
      </div>
      
  </layout>
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
  data(){
    return{
      showMonthList:false,
      selectedMonth:'month'
    }
  },
  methods:{
    toggleShow(){
      if(this.showMonthList == false){
       return this.showMonthList=true;
      }
      if(this.showMonthList == true){
        return  this.showMonthList=false;
      }
    },
    selectMonth(month){
      if(month == null){
          this.selectedMonth = 'month';
          this.showMonthList = false;
          return;
      }
      if(month != null){
          this.selectedMonth = month;
          this.showMonthList = false;
          return;
      }
    }
  }
})
</script>

