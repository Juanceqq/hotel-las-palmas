<template>
  <SiteSection>
    <template #background>
      <div class="w-full h-full bg-tertiary"></div>
    </template>
    <template #container>
      <div class="flex flex-col items-center px-10 2xl:px-48 py-10 lg:py-20">
        <div>
          <p ref="title" class="2xl:text-8xl xl:text-6xl text-5xl text-primary font-catchy"> Promociones y ofertas
          </p>
        </div>

        <div class="pt-20 grid md:grid-cols-2 xl:grid-cols-3 gap-5 xl:gap-10 ">
          <div v-for="promo in promos" :key="promo.id" ref="card" class="lg:pt-0 max-w-[500px]">
            <img :src="promo.srcImg" alt="" class="h-[300px] w-[500px] object-cover">
            <div class="border-solid border-2 border-t-0 border-primary">
              <div class="p-5 flex flex-col">
                <p class="font-coco text-primary text-2xl lg:text-3xl">{{ promo.title }}</p>
                <p class="text-md lg:text-xl pt-4 font-coco text-primary">
                  {{ promo.desc }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </template>
  </SiteSection>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from 'vue'
import SiteSection from '@/components/SiteSection.vue'
import gsap from "gsap"
import ScrollTrigger from "gsap/ScrollTrigger"

export default defineComponent({
  name: 'SiteSectionPromos',

  components: {
    SiteSection,
  },

  setup() {
    const title = ref(null)
    const card = ref(null)

    gsap.registerPlugin(ScrollTrigger)

    const promos = {
      earlyBird: {
        id: '1',
        srcImg: require('@/assets/reservation.webp'),
        title: 'Reserva temprana',
        desc: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Modi, ab commodi libero veritatis et omnis sapiente molestias vero assumenda cum',
      },
      members: {
        id: '2',
        srcImg: require('@/assets/spa-image.webp'),
        title: 'Club de miembros',
        desc: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Modi, ab commodi libero veritatis et omnis sapiente molestias vero assumenda cum',
      },
      promo: {
        id: '3',
        srcImg: require('@/assets/family-room.webp'),
        title: 'Tres noches, una gratis',
        desc: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Modi, ab commodi libero veritatis et omnis sapiente molestias vero assumenda cum',
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
      promos,
      title,
      card,
    }
  }
})
</script>
