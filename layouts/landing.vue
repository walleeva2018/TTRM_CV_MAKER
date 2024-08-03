<script lang="ts" setup>
const CVFY_IMAGE = 'https://werhere.nl/wp-content/uploads/2021/08/logo.png'

const { locale, t } = useI18n()
const route = useRoute()
const localePath = useLocalePath()
const HREF = `https://cvfy.xyz${route.path}`
const GITHUB = 'https://github.com/claudiabdm/cvfy'

useHead({
  htmlAttrs: {
    lang: locale,
  },
  title: t(String(route.meta.titleI18n)),
  meta: [
    {
      hid: 'description',
      name: 'description',
      content: t('description'),
    },
    {
      hid: 'author',
      name: 'author',
      content: 'werhere',
    },
    {
      hid: 'og:image',
      property: 'og:image',
      content: CVFY_IMAGE,
    },
    {
      hid: 'og:author',
      property: 'og:author',
      content: 'walleeva2018',
    },
    {
      hid: 'og:title',
      property: 'og:title',
      content: t('title-tag'),
    },
    {
      hid: 'og:description',
      property: 'og:description',
      content: t('description'),
    },

  ],
})
</script>

<template>
  <div class="font-landing text-fl-xs text-slate-800">
    <header class="p-fl-sm mb-fl-md max-w-screen-xl mx-auto">
      <nav class="font-light flex justify-between items-center">
        <LandingLogo />
        <section class="flex gap-fl-xs">
          <LandingLangSwitch />
        </section>
      </nav>
    </header>
    <main class="flex max-w-screen-xl mx-auto">
      <slot />
    </main>
  </div>
  <footer >
      <LandingFooterView />
     
    </footer>
</template>
