<template>
  <li>
    <a href="#" :class="classes">
      <BaseIcon :name="icon" class="w-6 h-6 mb-1.5" />
      <span class="text-xs">{{ label }}</span>
    </a>
  </li>
</template>

<script>
import BaseIcon from "@/components//BaseIcon.vue";
export default {
  components: {
    BaseIcon,
  },
  props: {
    isActive: Boolean,
    label: String,
    icon: String
  },
  computed: {
    classes() {
      return [
        this.isActive ? "text-red-500" : "text-gray-700",
        "flex",
        "flex-col",
        "items-center",
        "px-2",
        "py-5",
        "hover:bg-gray-100",
      ];
    },
  },
};
</script>
