<template>
  <SiteSection>
    <template #background>
      <div ref="background" class="bg-secondary w-full h-full" />
    </template>
    <template #container>
      <div class="xl:h-screen 3xl:h-auto py-10 px-10 2xl:px-48 grid items-center">
        <div class="flex flex-col items-center text-center xl:text-left gap-20 xl:grid xl:grid-cols-3">
          <div class="w-full h-full col-span-2 justify-between justify-items-center">
            <p ref="textOne" class="2xl:text-8xl xl:text-6xl text-5xl text-primary font-catchy">
              Bienvenido a tu<br class="hidden xl:block" />
              lujosa estancia lejos<br />
              de casa
            </p>
            <p ref="textTwo" class="2xl:text-3xl xl:text-2xl text-lg text-primary font-coco pt-10">
              Write Lorem ipsum dolor sit amet consectetur, adipisicing elit.
              Doloribus libero esse sint nobis quod labore optio suscipit
              voluptatum fugiat? Corrupti aliquid pariatur neque maxime tempore
              consequuntur quasi molestiae porro iusto.
            </p>
          </div>
          <div ref="vacationsImg" class="lg:h-[500px] xl:w-[400px] justify-self-end shadow-lg">
            <img src="../assets/drinkimage.webp" alt="bebida en la playa" class="h-full w-full object-cover rounded" />
          </div>
        </div>
      </div>
    </template>
  </SiteSection>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from "vue"
import SiteSection from "@/components/SiteSection.vue"
import gsap from "gsap"
import ScrollTrigger from "gsap/ScrollTrigger"

export default defineComponent({
  name: "SiteSectionWelcome",

  components: {
    SiteSection,
  },

  setup() {
    const textOne = ref(null);
    const textTwo = ref(null);
    const vacationsImg = ref(null);

    gsap.registerPlugin(ScrollTrigger);

    onMounted(() => {
      const textElements = [textOne.value, textTwo.value];

      gsap.fromTo(
        textElements,
        {
          y: 200,
          opacity: 0,
        },
        {
          ease: "expo.out",
          y: 0,
          opacity: 100,
          duration: 2,
          stagger: 0.2,
          scrollTrigger: textTwo.value,
        }
      );
      gsap.fromTo(
        vacationsImg.value,
        {
          opacity: 0,
        },
        {
          ease: "expo.in",
          opacity: 100,
          duration: 2,
          scrollTrigger: textTwo.value,
        }
      );
    });

    return {
      textOne,
      textTwo,
      vacationsImg,
    };
  },
});
</script>
