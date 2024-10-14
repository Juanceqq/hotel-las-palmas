<template>
  <SiteSection>
    <template #background>
      <div class="w-full h-full bg-primary" />
    </template>
    <template #container>
      <div id="siteFooter" class="flex flex-col px-10 2xl:px-48 py-10 lg:py-20">
        <div>
          <p class="2xl:text-7xl xl:text-5xl text-4xl text-white font-catchy">Hotel las palmas</p>
        </div>
        <div class="pt-20 grid md:grid-cols-2 lg:grid-cols-3 gap-5 xl:gap-10 justify-center ">
          <div class="border-white border">
            <div class="flex flex-col gap-3 p-5">
              <p class="text-2xl lg:text-3xl font-coco text-white">
                Reservaciones:
              </p>
              <div class="flex items-center gap-3 pt-3">
                <Icon icon="mdi:location" width="1.2em" height="1.2em" style="color: white" />
                <a href="https://maps.app.goo.gl/UxJH5CLuXtNgJdyt7" target="_blank" class="text-white font-coco ">
                  Av Miguel Aleman <p class="font-serif">232</p>.<br /> Mazatlan, Sinaloa
                </a>
              </div>
              <div class="flex items-center gap-3">
                <Icon icon="mingcute:cellphone-2-fill" width="1.2em" height="1.2em" style="color: white" />
                <a href="tel:123-456-7890" class="font-serif text-white">
                  1123-456-7890
                </a>
              </div>
              <div class="flex items-center gap-3">
                <Icon icon="material-symbols-light:mail" width="1.2em" height="1.2em" style="color: white" />
                <a href="mailto:hello@laspalmas.com" class="font-coco text-white">hello<p class="font-serif">@</p>
                  laspalmas.com</a>
              </div>
            </div>
          </div>
          <div class="border-white border">
            <div class="flex flex-col gap-3 p-5">
              <p class="text-2xl lg:text-3xl font-coco text-white">
                Horarios de oficina:
              </p>
              <div class="flex flex-col">
                <p class="font-coco text-white">Lunes a viernes:</p>
                <p class="font-coco text-white">
                  <a class="font-serif">9:00</a> AM a <a class="font-serif">6:00</a> PM
                </p>
              </div>
              <div class="flex flex-col">
                <p class="font-coco text-white">Sábado:</p>
                <p class="font-coco text-white">
                  <a class="font-serif">9:00</a> AM a <a class="font-serif">12:00</a> PM
                </p>
              </div>

            </div>
          </div>
          <div class="border-white border">
            <div class="flex flex-col gap-3 p-5">
              <p class="text-2xl lg:text-3xl font-coco text-white">
                Nuestras redes:
              </p>
              <div class="flex gap-12 pt-3">
                <a href="http://www.facebook.com" target="_blank"
                  class="w-14 h-14 hover:scale-105 border-white border rounded-full flex items-center justify-center">
                  <Icon icon="ic:baseline-facebook" width="384" height="384" style="color: white" class="p-2" />
                </a>
                <a href="http://www.x.com" target="_blank"
                  class="w-14 h-14 hover:scale-105 border-white border rounded-full flex items-center justify-center">
                  <Icon icon="prime:twitter" width="384" height="384" style="color: white" class="p-3" />
                </a>
                <a href="http://www.instagram.com" target="_blank"
                  class="w-14 h-14 hover:scale-105 border-white border rounded-full flex items-center justify-center">
                  <Icon icon="mdi:instagram" width="384" height="384" style="color: white" class="p-2" />
                </a>
              </div>
              <div class="py-3 mt-3 border-white text-white border rounded-full flex items-center justify-center">
                <p>Etiquetanos en tus fotos!</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </template>
  </SiteSection>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import SiteSection from '@/components/SiteSection.vue'
import { Icon } from "@iconify/vue"

export default defineComponent({
  name: 'SiteFooter.vue',

  components: {
    SiteSection,
    Icon
  },
})
</script>
