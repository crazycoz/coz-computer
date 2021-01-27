<template>
  <!-- <Layout> -->
    <div v-on:keyup.enter="auth" id="form" class="flex h-screen bg-gradient-to-r from-gray-700 to-black">
      <div class="w-96 m-auto bg-white shadow-lg flex-col p-4 space-y-4">
        <div class="flex justify-center">
          <div class="w-14 h-14 text-blue-500 ring bg-gray-200">
            <!-- <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-6-3a2 2 0 11-4 0 2 2 0 014 0zm-2 4a5 5 0 00-4.546 2.916A5.986 5.986 0 0010 16a5.986 5.986 0 004.546-2.084A5 5 0 0010 11z" clip-rule="evenodd" />
            </svg> -->
            <g-image class="mx-auto" fit="contain" width="1000" src="~/user.png"/>
          </div>
        </div>
        <div class="text-2xl text-center">Crazy Coz</div>
        <!-- <div class="space-y-1">
          <div class="text-gray-600 italic">Username:</div>
          <input class="bg-gray-100 text-xl p-1 w-full border text-center shadow-inner" type="text" placeholder="enter username" value="CrazyCoz">
        </div> -->
        <div class="space-y-1">
          <!-- <div class="text-gray-600 italic">Password:</div> -->
          <input autofocus :class="bg" class="border text-xl p-1 w-full text-center shadow-inner" placeholder="enter password" v-model="password" @change="reset" type="password">
          <div v-if="wrong" class="text-sm text-red-400 italic">Hint: look at fast internet through abraham's eyes...</div>
        </div>
        <div>
          <button type="submit" @click="auth" class="bg-blue-500 hover:bg-blue-400 focus:bg-gray-500 focus:ring-4 hover:shadow-inner rounded text-gray-50 py-2 px-3 font-bold float-right">
            <div v-if="!trying">
              Login
            </div>
            <div v-if="trying" class="animate-spin w-6">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd" />
              </svg>
            </div>
          </button>
        </div>
      </div>
    </div>
  <!-- </Layout> -->
</template>

<script>
export default {
  metaInfo: {
    title: 'Login'
  },

  data() {
    return {
      password: null,
      wrong: false,
      trying: false,
    }
  },

  methods: {
    auth: function() {
      this.trying = true
      setTimeout(() => {
        if (this.password === '379009') {
          this.$router.push('desktop')
        } else {
          this.wrong = true
          this.trying = false
        }
      }, 1500);
    },
    reset: function() {
      this.wrong = false
    }
  },

  computed: {
    bg() {
      return this.wrong ? 'bg-red-100' : 'bg-gray-100'
    }
  }
}
</script>
