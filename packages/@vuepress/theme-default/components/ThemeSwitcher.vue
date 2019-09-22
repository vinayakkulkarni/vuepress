<template>
  <div class="theme-switcher">
    <div class="svg-container" v-if="themeDark">
      <svg class="svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320.941 320.941" @click="toggleTheme()">
        <path d="M160.471 60.176c-55.299 0-100.294 44.995-100.294 100.294s44.995 100.294 100.294 100.294 100.294-44.995 100.294-100.294S215.769 60.176 160.471 60.176zm0 180.53c-44.241 0-80.235-35.994-80.235-80.235s35.994-80.235 80.235-80.235 80.235 35.994 80.235 80.235-35.994 80.235-80.235 80.235zM157.941 0H178v40.118h-20.059zM157.941 294.823H178v40.118h-20.059zM294.823 157.941h40.118V178h-40.118zM0 157.941h40.118V178H0zM248.698 61.622l28.36-28.36 14.18 14.18-28.36 28.36zM50.157 274.161l28.36-28.36 14.18 14.18-28.36 28.36zM255.696 252.274l14.18-14.18 28.36 28.36-14.18 14.18zM43.159 53.733l14.18-14.18 28.36 28.36-14.18 14.18z"/>
      </svg>
    </div>
    <div class="svg-container" v-else>
      <svg class="svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 473.411 473.411" @click="toggleTheme()">
        <path d="M405.786 417.081c-67.787-32.146-109.901-101.262-109.901-180.375S337.999 88.475 405.786 56.33a14.765 14.765 0 0 0 8.437-12.873 14.792 14.792 0 0 0-7.556-13.407C369.971 9.55 334.777 0 295.885 0 165.368 0 59.179 106.188 59.179 236.706s106.188 236.706 236.706 236.706c38.892 0 74.086-9.55 110.782-30.05a14.792 14.792 0 0 0 7.556-13.407 14.767 14.767 0 0 0-8.437-12.874zm-109.901 26.742c-114.206 0-207.118-92.911-207.118-207.118S181.679 29.588 295.885 29.588c25.341 0 48.269 4.479 71.731 14.245-63.15 41.031-101.32 112.516-101.32 192.872s38.17 151.842 101.32 192.872c-23.462 9.767-46.39 14.246-71.731 14.246z"/>
      </svg>
    </div>
  </div>
</template>

<script>

export default {
  name: 'ThemeSwitcher',
  props: {
    themeDark: {
      required: true,
      type: Boolean
    }
  },

  methods: {
    toggleTheme () {
      this.themeDark ? this.$emit('theme-toggled', false) : this.$emit('theme-toggled', true)
    }
  }
}
</script>

<style scoped>
.theme-switcher {
  padding: 0 0.75rem;
  user-select: none;
}
.svg-container {
  display: inline-block;
  vertical-align: middle;
  cursor: pointer;
}
.svg {
  height: 1rem;
  width: 1rem;
  fill: currentColor;
}
</style>
