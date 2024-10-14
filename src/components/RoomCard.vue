<template>
  <div class="max-w-[500px]">
    <img :src="imgSrc" alt="" class="lg:w-[500px]">
    <div class="border-solid border-2 border-t-0 border-primary">
      <div class="p-3 flex flex-col">
        <p class="text-lg lg:text-xl pl-1 font-coco text-primary"> <a class="font-serif">{{ capacity }}</a> personas</p>
        <p class="lg:pt-7 text-3xl lg:text-5xl font-coco text-primary">{{ title }}</p>
        <p class="text-primary pl-1 text-lg lg:text-xl font-coco">From <a class="font-serif">${{ price }}</a> a night
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'RoomCard',
  props: {
    imgSrc: {
      type: String,
      required: true,
    },
    capacity: {
      type: [Number, String],
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    price: {
      type: [Number, String],
      required: true,
    }
  },
  setup() {


    return {}
  }
})
</script>
