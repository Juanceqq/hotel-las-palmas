<template>
  <SiteSection>
    <template #background>
      <div class="w-full h-full bg-tertiary" />
    </template>
    <template #container>
      <div class="flex flex-col items-center px-10 2xl:px-48 py-10 lg:py-20">
        <div>
          <p ref="title" class="2xl:text-8xl xl:text-6xl text-5xl text-primary font-catchy"> Alojamientos </p>
        </div>
        <div class="pt-20 grid md:grid-cols-2 lg:grid-cols-3 gap-5 xl:gap-10 ">
          <div v-for="room in rooms" :key="room.id" ref="card">
            <RoomCard :imgSrc="room.imgSrc" :capacity="room.capacity" :price="room.price" :title="room.title"
              class="hover:scale-105 hover:shadow-xl transition duration-500" />
          </div>
        </div>
      </div>
    </template>
  </SiteSection>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from "vue";
import SiteSection from "@/components/SiteSection.vue";
import RoomCard from "@/components/RoomCard.vue"
import gsap from "gsap"
import ScrollTrigger from "gsap/ScrollTrigger"

export default defineComponent({
  name: "SiteSectionAccommodations",

  components: {
    SiteSection,
    RoomCard,
  },

  setup() {
    const title = ref(null)
    const card = ref(null)

    gsap.registerPlugin(ScrollTrigger)

    const rooms = {
      deluxeRoom: {
        id: '1',
        imgSrc: require('@/assets/deluxe-room.webp'),
        capacity: 2,
        price: 200,
        title: 'Suite deluxe'
      },
      familyRoom: {
        id: '2',
        imgSrc: require('@/assets/family-room.webp'),
        capacity: 4,
        price: "250",
        title: 'Suite familiar'
      },
      jacuzziRoom: {
        id: '3',
        imgSrc: require('@/assets/jacuzzi-room.webp'),
        capacity: 2,
        price: "400",
        title: 'Suite jacuzzi'
      }
    }

    onMounted(() => {
      gsap.fromTo(
        title.value,
        {
          y: 200,
          opacity: 0,
        },
        {
          ease: 'expo.out',
          y: 0,
          opacity: 100,
          duration: 2,
          scrollTrigger: title.value
        }
      )
      gsap.fromTo(
        card.value,
        {
          y: 200,
          opacity: 0,
        },
        {
          ease: 'expo.out',
          y: 0,
          opacity: 100,
          duration: 2,
          scrollTrigger: title.value,
          stagger: 0.2
        }
      )
    })

    return {
      rooms,
      title,
      card,
    };
  },
});
</script>
