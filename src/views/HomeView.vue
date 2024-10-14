<template>
  <SiteSectionHero />
  <SiteSectionWelcome />
  <SiteSectionAccommodations />
  <SiteSectionFamily />
  <SiteSectionPromos />
  <SiteFooter />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SiteSectionHero from "@/components/SiteSectionHero.vue";
import SiteSectionWelcome from "@/components/SiteSectionWelcome.vue";
import SiteSectionAccommodations from "@/components/SiteSectionAccommodations.vue";
import SiteSectionFamily from "@/components/SiteSectionFamily.vue";
import SiteSectionPromos from "@/components/SiteSectionPromos.vue";
import SiteFooter from "@/components/SiteFooter.vue";

export default defineComponent({
  name: "HomeView",
  components: {
    SiteSectionHero,
    SiteSectionWelcome,
    SiteSectionAccommodations,
    SiteSectionFamily,
    SiteSectionPromos,
    SiteFooter
  },
});
</script>
