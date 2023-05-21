<template>
  <div class="flex w-full h-full mr-2">
    <TheSearchInput/>
    <TheSearchButton/>
  </div>
</template>

<script>
import TheSearchInput from '@/components/TheSearchInput.vue'
import TheSearchButton from '@/components/TheSearchButton.vue'
export default {
    components: {
        TheSearchInput,
        TheSearchButton
    }
}
</script>