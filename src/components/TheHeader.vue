<template>
  <header class="flex justify-between fixed z-30 w-full">
    <div class="lg:w-1/4 flex">
      <div class="flex items-center xl:w-64 xl:bg-white pl-4">
        <button
          @click="$emit('toggleSidebar')"
          class="mr-3 sm:ml-2 sm:mr-6 focus:outline-none"
        >
          <BaseIcon name="menu" />
        </button>
        <LogoMain />
      </div>
    </div>
    <TheSearchMobile
      v-if="isMobileSearchShown"
      @close="closeMobileSearch"
    />
    <div
      v-else
      class="hidden sm:flex items-center justify-end p-2.5 pl-8 md:pl-12 md:px-8 flex-1 lg:px-0 lg:w-1/2 max-w-screen-md"
    >
      <TheSearch />
      <BaseTooltip text="Search with your voice">
        <button class="p-2 focus:outline-none">
          <BaseIcon name="microphone" class="w-5 h-5" />
        </button>
      </BaseTooltip>
    </div>
    <div
      class="flex items-center justify-end lg:w-1/4 sm:space-x-3 p-2 sm:px-4"
    >
      <BaseTooltip text="Search with your voice">
        <button class="sm:hidden p-2 focus:outline-none">
          <BaseIcon name="microphone" class="w-5 h-5" />
        </button>
      </BaseTooltip>
      <BaseTooltip text="Search">
        <button
          @click.stop="isMobileSearchActive = true"
          class="sm:hidden p-2 focus:outline-none"
        >
          <BaseIcon name="search" class="w-5 h-5" />
        </button>
      </BaseTooltip>
      <TheDropdownApps />
      <TheDropdownSettings />
      <ButtonLogin />
    </div>
  </header>
</template>

<script>
import TheDropdownApps from "@/components/TheDropdownApps.vue";
import TheDropdownSettings from "@/components/TheDropdownSettings.vue";
import LogoMain from "@/components/LogoMain.vue";
import TheSearch from "@/components/TheSearch.vue";
import TheSearchMobile from "@/components/TheSearchMobile.vue";
import ButtonLogin from "@/components/ButtonLogin.vue";
import BaseIcon from "@/components/BaseIcon.vue";
import BaseTooltip from "@/components/BaseTooltip.vue";
export default {
  components: {
    TheDropdownApps,
    TheDropdownSettings,
    LogoMain,
    TheSearch,
    TheSearchMobile,
    ButtonLogin,
    BaseIcon,
    BaseTooltip,
  },
  emits: {
    toggleSidebar: null,
  },
  data() {
    return {
      isSmallScreen: false,
      isMobileSearchActive: false,
    };
  },
  computed: {
    isMobileSearchShown() {
      return this.isSmallScreen && this.isMobileSearchActive
    }
  },
  mounted() {
    this.onResize();
    window.addEventListener("resize", this.onResize);
  },
  methods: {
    onResize() {
      if (window.innerWidth < 640) {
        this.isSmallScreen = true;
        return;
      }
      this.closeMobileSearch();
      this.isSmallScreen = false;
    },
    closeMobileSearch() {
      this.isMobileSearchActive = false;
    },
  },
};
</script>
