<template>
  <section :class="classes">
    <div class="border-t border-b px-4 max-w-screen-2xl m-auto">
      <div class="py-3 flex space-x-3 overflow-auto text-sm whitespace-nowrap">
        <CategoryItem
          v-for="(category, id) in categories"
          :key="id"
          :category="category"
          :isActive="category === 'All'"
        />
      </div>
    </div>
  </section>
</template>

<script>
import CategoryItem from "@/components/CategoryItem.vue";
export default {
  components: {
    CategoryItem,
  },
  props: {
    isSidebarOpen: Boolean,
  },
  data() {
    return {
      categories: [
        "All",
        "Trucks",
        "Tools",
        "Machines",
        "Engines",
        "Snow",
        "Ships",
        "Roads",
        "Tanks",
        "Building",
        "Mars",
        "Woodworking",
        "Songs",
        "TV Shows",
        "Football",
        "Planes",
        "Live",
        "Streets",
        "Math",
        "Programming",
      ],
    };
  },
  computed: {
    classes() {
      return [
        this.isSidebarOpen ? "xl:pl-64" : "md:pl-24",
        "pt-14",
        "w-full",
        "fixed",
        "bg-white",
        "bg-opacity-95",
        "z-10",
      ];
    },
  },
};
</script>
