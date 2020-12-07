<template>
  <div class="flex flex-wrap -mt-4 sm:-m-4 -mt-4 ">
    <div v-for="post of data" class="p-10 md:w-1/3 md:mb-0 mb-6 flex flex-col ">
      <div class="pattern-dots-md gray-light">
        <div
          class="rounded bg-gray-800 p-4 transform translate-x-6 -translate-y-6"
        >
          <div class="flex-grow">
            <h2 class=" text-xl title-font font-medium mb-3">{{post.title}}</h2>
            <p class="leading-relaxed text-sm text-justify">
              {{post.content}}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  head: {
    data: null,
    title: 'Front'
  },
  data(){
    return{
      data: null,
    }
  },
  mounted(){
    axios.get('http://127.0.0.1:8000/api/posts').then(response => this.data = response.data);
  }
}
</script>
