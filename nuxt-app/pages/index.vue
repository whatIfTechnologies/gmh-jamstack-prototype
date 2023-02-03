<template>
  <div class="container">
    <div class="flex flex-col items-center">
      <h1 class="mb-4 text-pink-700 font-bold">
        {{ home.data.attributes.Title }}
      </h1>
      <h2 class="font-bold mb-8">{{ home.data.attributes.Subtitle }}</h2>
      <div class="mb-4 text-green-700">
        {{ home.data.attributes.Body }}
      </div>
      <img :src="`http://localhost:1337${home.data.attributes.Image.data.attributes.url}`" class="w-1/4 mb-6" alt="Featured Image">
      <LocaleSwitcher />
    </div>
  </div>
</template>

<script>
import LocaleSwitcher from '~/components/LocaleSwitcher.vue'
export default {
  components: {
    LocaleSwitcher
  },
  async asyncData ({ $strapi, i18n }) {
    const home = await $strapi.$home.find({ locale: i18n.locale, populate: 'Image' })
    console.log('hello strapi')
    // eslint-disable-next-line quotes
    return {
      home
    }
  }
}
</script>

<style>

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

</style>
