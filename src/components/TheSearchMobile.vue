<template>
  <div class="fixed bg-white w-full h-14 p-3 z-10 flex">
    <BaseTooltip @click="$emit('close')" text="Back">
      <button class="mr-2 p-2 focus:outline-none">
        <BaseIcon name="arrowLeft" class="w-5 h-5" />
      </button>
    </BaseTooltip>
    <TheSearch />
    <BaseTooltip text="Search with your voice" left>
      <button class="p-2 focus:outline-none">
        <BaseIcon name="microphone" class="w-5 h-5" />
      </button>
    </BaseTooltip>
  </div>
</template>

<script>
import BaseIcon from "@/components/BaseIcon.vue";
import BaseTooltip from "@/components/BaseTooltip.vue";
import TheSearch from "@/components/TheSearch.vue";
export default {
  components: {
    BaseIcon,
    BaseTooltip,
    TheSearch,
  },
  mounted() {
    window.addEventListener('click', this.onClick)
  },
  unmounted() {
    window.removeEventListener('click', this.onClick)
  },
  methods: {
    onClick(event) {
      if (!this.$el.contains(event.target)) {
        this.$emit('close')
      }
    }
  }
};
</script>
