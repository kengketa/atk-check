<template>
  <layout>
    <div>
      <!--      <p v-for="(product,index) in products" :key="index">{{ product.surname }}</p>-->
      <d v-for="(month,index) in months" :key="index">
        <div class="flex items-end gap-4 mb-4">
          <p>{{ month.name }}</p>
          <div class="flex flex-wrap gap-2">
            <p
              class="border border-gray-200 rounded-md px-4 py-2 cursor-pointer hover:bg-gray-300 transition transform duration-200 ease-in-out hover:scale-150"
              v-for="index in month.numberOfDays">
              {{ index }}</p>
          </div>
        </div>
      </d>
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
  data() {
    return {
      products: [
        {id: 1, name: 'A', surname: 'aaaa'},
        {id: 2, name: 'B', surname: 'bbbb'},
        {id: 3, name: 'C', surname: 'cccc'},
        {id: 4, name: 'D', surname: 'dddd'},
        {id: 5, name: 'E', surname: 'eeee'},
        {id: 6, name: 'F', surname: 'ffff'},
        {id: 7, name: 'G', surname: 'gggg'},
      ],
      months: [
        {id: 1, name: 'Jan', numberOfDays: 31},
        {id: 2, name: 'Feb', numberOfDays: 29},
        {id: 3, name: 'Mar', numberOfDays: 31},
      ]
    }
  },
  methods: {}
})
</script>
