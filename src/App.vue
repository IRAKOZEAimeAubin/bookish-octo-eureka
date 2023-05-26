<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Modal from './components/Modal.vue';
</script>

<template>
  <div class="flex flex-col w-[100%] items-center mt-4 gap-3">
    <h1 class="text-center bg-amber-200 text-slate-950 w-28 p-2 rounded-md font-extrabold">{{ title }}</h1>
    <HelloWorld />
    <input type="text" ref="name" class="border-slate-400 border-[1px] rounded-sm outline-none py-1 px-2 placeholder:italic" placeholder="John Doe...">
    <button class="bg-sky-800 text-slate-200 px-3 py-2 rounded-md hover:text-slate-50 hover:bg-sky-700 uppercase font-bold tracking-widest font-mono" @click="handleClick">Click Me!</button>
  </div>
  <div v-if="showModal">
    <Modal theme="dark" @close="handleClick">
      <template v-slot:links>
        <a href="#" class="text-sky-400 uppercase">sign up</a>
        <a href="#" class="text-sky-400 uppercase">login</a>
      </template>
      <h1 class="text-rose-400 font-medium">I am modal!</h1>
    </Modal>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {
    HelloWorld, Modal
  },
  data () {
    return {
      title: "Brainy says:",
      showModal: false
      }
  },
  methods: {
    handleClick () {
      this.showModal = !this.showModal
      }
    }
  }
</script>
