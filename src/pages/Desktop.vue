<template>
  <div class="flex h-screen w-screen bg-gradient-to-r from-gray-700 to-black p-4">
    <div class="w-full h-full shadow-lg flex-col p-4 space-y-4">
      <g-image class="mx-auto" fit="contain" width="1000" src="~/background.jpg"/>
      <div>
        <button type="submit" @click="back" class="bg-red-500 hover:bg-red-400 focus:bg-gray-500 focus:ring-4 hover:shadow-inner rounded text-gray-50 py-2 px-3 font-bold float-right">Logout</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  metaInfo: {
    title: 'Desktop'
  },

  methods: {
    back: function() {
      this.$router.push('/')
    },
  },
}
</script>
