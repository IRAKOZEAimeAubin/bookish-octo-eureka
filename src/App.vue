<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="flex flex-col w-[100%] items-center mt-4 gap-3">
    <h1 class="text-center bg-amber-200 text-slate-950 w-28 p-2 rounded-md font-extrabold">{{ title }}</h1>
    <HelloWorld />
    <input type="text" ref="name" class="border-slate-400 border-[1px] rounded-sm outline-none py-1 px-2 placeholder:italic" placeholder="John Doe...">
    <button class="bg-sky-800 text-slate-200 px-3 py-2 rounded-md hover:text-slate-50 hover:bg-sky-700" @click="handleClick">Click Me</button>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {
    HelloWorld
  },
  data () {
    return {
        title:"Brainy says: "
      }
  },
  methods: {
    handleClick () {
      console.log( this.$refs.name.value )
      }
    }
  }
</script>
