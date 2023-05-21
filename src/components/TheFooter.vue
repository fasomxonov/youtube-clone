<template>
  <div>
    <a href="#" class="mr-2" v-for="(list, id) in lists.slice(0, 7)" :key="id" >{{ list }}</a>
  </div>
  <div>
    <a href="#" class="mr-2" v-for="(list, id) in lists.slice(7)" :key="id">{{ list }}</a>
  </div>
  <div class="font-normal text-gray-500">&copy; 2021 Google LLC</div>
</template>

<script>
export default {
    data() {
        return {
            lists: [
                'About',
                'Press',
                'Copyright',
                'Contact us',
                'Creators',
                'Advertise',
                'Developers',
                'Terms',
                'Privacy',
                'Policy & Safety',
                'How YouTube works',
                'Test new features'
            ]
        }
    },
}
</script>