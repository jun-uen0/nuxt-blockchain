<template>
  <div>
    <div class="shadow">
    <nav class="bg-white-500">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-24 lg:h-30">
        <div class="flex items-center">
        <div class="flex-shrink-0">
          <img
          class="h-8 w-20 object-contain"
          src="/my-profile-pic-no-bg.png"
          alt="notta-white-logo"
          >
        </div>
        <div class="hidden md:block">
        </div>
        </div>
        
        <p>ここに何かしら面白い機能をつけたいと考えてます..</p>
        <!-- <div class="hidden md:block">
        <div class="ml-4 flex items-center md:ml-6">
          <div class="ml-3 relative">
          <div>
            <button
            @click="toggle"
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:bg-gray-700 focus:text-white"
          >
            <svg
            :class="[isOpen ? 'hidden' : 'block', 'h-6 w-6']"
            stroke="currentColor"
            fill="none"
            viewBox="0 0 24 24"
            >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            ></path>
            </svg>
            <svg
            :class="[isOpen ? 'block' : 'hidden', 'h-6 w-6']"
            stroke="currentColor"
            fill="none"
            viewBox="0 0 24 24"
            >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            ></path>
            </svg>
          </button>
          </div>
          <transition
            enter-active-class="transition ease-out duration-100"
            enter-class="transform opacity-0 scale-95"
            enter-to-class="transform opacity-100 scale-100"
            leave-active-class="transition ease-in duration-75"
            leave-class="transform opacity-100 scale-100"
            leave-to-class="transform opacity-0 scale-95"
          >
            <div
            v-show="isOpen"
            class="origin-top-right absolute right-0 mt-2 w-48 rounded-md shadow-lg"
            >
            <div
              class="py-1 rounded-md bg-white shadow-xs"
              role="menu"
              aria-orientation="vertical"
              aria-labelledby="user-menu"
            >
              <a
              @click="goToLogin"
              class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
              role="menuitem"
              >ログイン</a>
              <a
              @click="goToSignup"
              class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
              role="menuitem"
              >新規会員登録</a>
            </div>
            </div>
          </transition>
          </div>
        </div>
        </div> -->
        <div class="-mr-2 flex md:hidden">
        <!-- スマホメニュー -->
        <!-- <button
          @click="toggle"
          class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:bg-gray-700 focus:text-white"
        >
          <svg
          :class="[isOpen ? 'hidden' : 'block', 'h-6 w-6']"
          stroke="currentColor"
          fill="none"
          viewBox="0 0 24 24"
          >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          ></path>
          </svg>
          <svg
          :class="[isOpen ? 'block' : 'hidden', 'h-6 w-6']"
          stroke="currentColor"
          fill="none"
          viewBox="0 0 24 24"
          >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          ></path>
          </svg>
        </button> -->
        </div>
      </div>
      </div>
      <div :class="[isOpen ? '' : 'hidden', 'md:hidden']">
      <div class="pb-3 border-t border-white">
        <div class="flex items-center px-5">
        </div>
        <div class="mt-3 px-2">
        <a
          @click="goToLogin"
          class="block px-3 py-2 rounded-md text-base font-bold text-white hover:text-white hover:bg-gray-700 focus:outline-none focus:text-white focus:bg-gray-700"
        >ログイン</a>
        <a
          @click="goToSignup"
          class="mt-1 block px-3 py-2 rounded-md text-base font-bold text-white hover:text-white hover:bg-gray-700 focus:outline-none focus:text-white focus:bg-gray-700"
        >新規会員登録</a>
        </div>
      </div>
      </div>
    </nav>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    isOpen: false
    }
  },
  methods: {
    toggle () {
      this.isOpen = !this.isOpen
    },
    goToLogin () {
      this.$router.push("/authentication/log-in");
    },
    goToSignup () {
      this.$router.push("/authentication/sign-up");
    }
  }
}
</script>