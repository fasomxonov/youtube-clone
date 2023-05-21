<template>
  <aside :class="classes">
    <section>
      <ul>
        <SidebarCompactNavItem
          v-for="(navItem, index) in navItems"
          :key="index"
          :icon="navItem.icon"
          :label="navItem.label"
          :is-active="navItem.isActive"
        />
      </ul>
    </section>
  </aside>
</template>

<script>
import SidebarCompactNavItem from "@/components/SidebarCompactNavItem.vue";
export default {
  components: {
    SidebarCompactNavItem,
  },
  data() {
    return {
      navItems: [
        {
          label: 'Home',
          icon: 'home',
          isActive: true
        },
        {
          label: 'Trending',
          icon: 'fire',
          isActive: false
        },
        {
          label: 'Subscriptions',
          icon: 'collection',
          isActive: false
        },
        {
          label: 'Library',
          icon: 'duplicate',
          isActive: false
        },
        {
          label: 'History',
          icon: 'clock',
          isActive: false
        },
      ]
    }
  },
  computed: {
    classes() {
      return [
        "min-h-screen",
        "overflow-auto",
        "fixed",
        "top-0",
        "pt-14",
        "bg-white",
        "z-20",
      ];
    },
  },
};
</script>
