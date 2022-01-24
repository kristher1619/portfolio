<template>
  <div>
    <a
      v-if="canShowEmail"
      class="tw-inline-flex tw-border-2 tw-border-gray-300 tw-pl-4 tw-pr-8 tw-py-2 tw-rounded-md"
      href="mailto: kristher.vidal@gmail.com"
    >
      kristher.vidal@gmail.com
    </a>
    <button
      v-else
      class="tw-flex tw-text-white tw-bg-green-500 tw-pl-4 tw-pr-8 tw-py-2 tw-rounded-md tw-text-lg tw-items-center"
      @click="togglePopup"
    >
      <img src="/icons/mail.svg" alt="" class="tw-mr-2" />
      Contact
    </button>
    <div v-show="showPopupModal" class="popup-email">
      <p class="tw-mb-1">Are you human?</p>
      {{ number1 }} + {{ number2 }} =
      <input v-model="sum" class="sum" />
      <div>
        <button
          class="tw-mt-2 tw-w-full tw-justify-center tw-flex tw-text-white tw-bg-green-500 tw-p-1 tw-rounded-sm tw-text-xs"
          @click="showEmail()"
        >
          Show Email
        </button>
      </div>
      <p v-show="hasError" class="tw-text-red-500 tw-mt-2">Invalid Answer!</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PopupEmail',
  data() {
    return {
      number1: 0,
      number2: 0,
      sum: '',
      hasError: false,
      canShowEmail: false,
      showPopupModal: false
    }
  },
  methods: {
    showEmail() {
      if (parseInt(this.sum) === this.number1 + this.number2) {
        this.canShowEmail = true
        this.showPopupModal = false
        this.hasError = false
        return
      }
      this.canShowEmail = false
      this.hasError = true
    },
    togglePopup() {
      if (this.showPopupModal) {
        this.showPopupModal = false
        this.canShowEmail = false
        return
      }
      this.showPopup()
    },
    showPopup() {
      this.number1 = Math.floor(Math.random() * 10)
      this.number2 = Math.floor(Math.random() * 10)
      this.showPopupModal = true
    }
  }
}
</script>

<style scoped>
.popup-email {
  @apply tw-absolute tw-bg-white tw-p-4 tw-rounded-md tw-shadow-md tw-mt-2 tw-text-sm;
}

.sum {
  width: 40px;
  @apply tw-border tw-border-gray-200;
}
</style>
