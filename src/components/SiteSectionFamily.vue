<template>
  <SiteSection>
    <template #background>
      <div class="w-full h-full bg-secondary" />
    </template>
    <template #container>
      <div class="flex flex-col text-center lg:text-left lg:grid lg:grid-cols-3 px-10 2xl:px-48 py-10 lg:py-20">
        <div class="flex flex-col">
          <p ref="title" class="2xl:text-8xl xl:text-6xl text-5xl text-primary font-catchy">Suite familiar</p>
          <p ref="desc" class="2xl:text-3xl xl:text-2xl text-lg text-primary font-coco pt-10">Lorem ipsum dolor sit amet
            consectetur adipisicing elit. Iure, labore. Molestiae,
            pariatur? Consequuntur.
          </p>
        </div>
        <div class="col-span-2 pt-10 lg:pt-0">
          <img ref="image" src="@/assets/family-room.webp" alt="" class="A room by the beach">
          <div ref="imageText" class="border-solid border-2 border-primary mt-5">
            <div class="p-5 flex flex-col text-center">
              <p class="text-md lg:text-xl pl-1 font-coco text-primary">Lorem ipsum dolor sit, amet consectetur
                adipisicing elit. Modi, ab commodi libero veritatis et omnis sapiente molestias vero assumenda cum,
                optio qui nesciunt ullam blanditiis placeat error nemo accusantium voluptatem.</p>
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
  name: "SiteSectionFamily",

  components: {
    SiteSection,
  },

  setup() {
    const title = ref(null)
    const desc = ref(null)
    const image = ref(null)
    const imageText = ref(null)

    gsap.registerPlugin(ScrollTrigger)

    onMounted(() => {
      const textElements = [title.value, desc.value]

      gsap.fromTo(
        textElements,
        {
          y: 200,
          opacity: 0,
        },
        {
          ease: 'expo.out',
          y: 0,
          opacity: 100,
          duration: 2,
          stagger: 0.2,
          scrollTrigger: desc.value
        }
      )
      gsap.fromTo(
        image.value,
        {
          // y: 200,
          opacity: 0,
        },
        {
          ease: 'expo.inOut',
          y: 0,
          opacity: 100,
          duration: 2,
          scrollTrigger: image.value,
        }
      )
      gsap.fromTo(
        imageText.value,
        {
          rotationY: -90,
          opacity: 0
        },
        {
          ease: 'expo.out',
          opacity: 100,
          rotationY: 0,
          duration: 2,
          scrollTrigger: imageText.value,
        }
      )
    })

    return {
      title,
      desc,
      image,
      imageText,
    }
  }
})
</script>
