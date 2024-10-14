<template>
  <SiteSection>
    <template #background>
      <div class="bg-primary absolute w-full h-full opacity-50" />
      <img src="@/assets/hero.webp" class="w-full h-full object-cover" />
    </template>
    <template #container>
      <div class="w-full h-screen max-h-screen-lg flex flex-col items-center justify-center gap-10">
        <div class="flex flex-col text-white text-center font-catchy gap-10 lg:gap-10 px-4">
          <p id="textOne" ref="textOne" class="text-3xl lg:text-5xl">Bienvenido a</p>
          <p ref="textTwo" class="text-8xl lg:text-9xl">Hotel Las Palmas</p>
          <p ref="textThree" class="text-2xl lg:text-3xl">Spa & Resort</p>

        </div>
        <!-- <div>
          <button ref="contactButton"
            class="font-coco font-semibold text-md tracking-wider hover:bg-primary-400 hover:text-white transition-colors duration-500 bg-white text-primary px-10 py-3 rounded-sm">
            Contáctanos
          </button>
        </div> -->
      </div>
    </template>
  </SiteSection>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from 'vue';
import SiteSection from '@/components/SiteSection.vue';
import gsap from 'gsap';

export default defineComponent({
  name: 'SiteSectionHero',

  components: {
    SiteSection,
  },

  setup() {
    const textOne = ref(null)
    const textTwo = ref(null)
    const textThree = ref(null)

    onMounted(() => {
      const textElements = [textOne.value, textTwo.value, textThree.value]

      const tl = gsap.timeline({
        delay: 0
      })

      tl.fromTo(
        textElements,
        {
          y: 200,
          opacity: 0
        },
        {
          ease: 'expo.out',
          y: 0,
          opacity: 100,
          duration: 2,
          stagger: 0.1,
        }
      )
    })


    return {
      textOne,
      textTwo,
      textThree,
    }
  }
});
</script>
