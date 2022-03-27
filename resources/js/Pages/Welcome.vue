<template>
  <layout>
    <label for="price" class="block text-sm font-medium text-gray-700 mt-4">ค้นหา </label>
    <div>
  <div class="mt-4 rounded-md">
    <div class="relative">
      <input type="text" name="price" id="price" class="text-xl text-gray-700 focus:ring-indigo-500 focus:border-indigo-500 block w-1/3 px-10 rounded-md" ค้นหา="">
      <div class="text-gray-400 text-gray-400 w-10 absolute top-0 py-3 pl-3">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
        </svg>
      </div>
    </div>
  </div>
</div>
<div class="bg-white px-4 py-3 flex items-center justify-between border-gray-200 sm:px-6">
  <div class="flex-1 flex justify-between sm:hidden">
    <a href="#" class="relative inline-flex items-center px-4 py-2 border border-gray-300 text-sm font-medium rounded-md text-gray-700 bg-white hover:bg-gray-50"> Previous </a>
    <a href="#" class="ml-3 relative inline-flex items-center px-4 py-2 border border-gray-300 text-sm font-medium rounded-md text-gray-700 bg-white hover:bg-gray-50"> Next </a>
  </div>
  <div class="hidden sm:flex-1 sm:flex sm:justify-between mt-6">
    <div class="relative flex gap-4"> 
      <div
        @click="toggleShow()"
        class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
        rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500 transition duration-500 transform ease-in-out hover:scale-90 hover:text-white">
        <p>{{ selectedMonth.id == 0 ? 'month' :selectedMonth.name }}</p>
      </div>
      <div class="flex flex-wrap gap-1 w-full" v-if="selectedMonth.id != 0">
        <div v-for="index in selectedMonth.numberOfDays" :key="index" class="border border-gray-500 flex justify-center items-center px-4 py-2 rounded-md cursor-pointer hover:bg-gray-200 transition transform hover:scale-110">{{index}}</div>
      </div>
      <div v-if="showMonthList" class="absolute top-10 z-50" id="month-group"> 
        <div
          v-for="(month,index) in months" :key="index"
          @click="selectMonth(month)"
          class="border border-gray-500 w-16 h-10 flex justify-center items-center bg-gray-200
          rounded-md shadow shadow-md cursor-pointer hover:bg-gray-500">
          <p>{{ month.name }}</p>
        </div>
      </div>
    </div>
  </div>
</div>
<h2 class="text-2xl font-extrabold text-gray-900 mt-8">Atkcheck</h2>
<div class="flex gap-4 flex-wrap">
  <div v-for="(atkTest,index) in atkTests" :key="index">
    <div class="w-60 relative rounded-md overflow-hidden">
        <img class="w-full object-cover" :src="atkTest.image" alt="">
        <div class="flex justify-center bg-gray-200 py-2">
          <p>{{atkTest.studentName}}</p>
        </div>
        <div class="absolute top-0 right-0 bg-gray-200 w-6 h-6 flex justify-center items-center">
            <p class="text-sm">1</p>
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

export default defineComponent({
  components: {
    Head,
    Link,
  },
  data(){
    return{
      showMonthList:false,
      selectedMonth: {id:0,name:'None',numberOfDays:0},
       months: [
         {id:0,name:'None',numberOfDays:0},
         {id:1,name:'Jan',numberOfDays:31},
         {id:2,name:'Feb',numberOfDays:29},
         {id:3,name:'Mar',numberOfDays:31},
         {id:4,name:'Apr',numberOfDays:30},
         {id:5,name:'May',numberOfDays:31},
         {id:6,name:'Jun',numberOfDays:30},
         {id:7,name:'Jul',numberOfDays:31},
         {id:8,name:'Aug',numberOfDays:31},
         {id:9,name:'Sep',numberOfDays:30},
         {id:10,name:'Oct',numberOfDays:31},
         {id:11,name:'Nov',numberOfDays:30},
         {id:12,name:'DecP',numberOfDays:31},
       ],
       atkTests:[ 
         {id:1,studentName:'Name 1',date:'10/1/2022',image:'https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg'},
         {id:2,studentName:'Name 2',date:'11/1/2022',image:'https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg'},
         {id:3,studentName:'Name 3',date:'12/1/2022',image:'https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg'},
         {id:4,studentName:'Name 4',date:'13/1/2022',image:'https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg'},
         {id:5,studentName:'Name 5',date:'14/1/2022',image:'https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg'},
         {id:6,studentName:'Name 6',date:'15/1/2022',image:'https://www.sikarin.com/wp-content/uploads/2021/08/3813357-1024x683.jpg'},
]
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
      console.log(month);
      this.selectedMonth = month;
      return this.showMonthList = false;
    }
  }
})
</script>

