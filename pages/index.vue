<script lang="ts" setup>
const localePath = useLocalePath()
const { t, locale } = useI18n()
definePageMeta({
  titleI18n: 'title-tag',
  layout: 'landing',
})
useHead({
  htmlAttrs: {
    lang: locale,
  },
  title: t('title-tag'),
})
</script>

<template>
  <div class="flex flex-col min-h-screen">
    <main class="flex-grow">
      <section
        class="min-h-[calc(100vh-var(--header-height))] flex flex-col justify-center items-center text-center mx-auto gap-8 flex-wrap font-bold p-fl-md">
        <div class="leading-normal">
          <h2 class="mb-2 text-fl-2xl">
            {{ $t('hero-title-1') }} <span
              class="text-nowrap text-transparent bg-gradient-to-bl from-red-800 to-fuchsia-700 bg-clip-text">{{
              $t('hero-title-2') }}</span><br> {{ $t('hero-title-3') }}<span
              class="text-fl-2xl text-transparent bg-gradient-to-br from-red-800 to-fuchsia-700 bg-clip-text">.</span>
          </h2>
          <p class="mb-4 font-light max-w-prose mx-auto">
            {{ $t('hero-paragraph') }}
          </p>
          <LandingLink :to="localePath('create')" cta>
            <span>{{ $t('get-started') }}</span>
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2"
              stroke="currentColor" class="size-4">
              <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
            </svg>
          </LandingLink>
        </div>
        <LandingHeroImage />
        <LandingProcessView />
        <div class="text-xs font-light">
          Made with ♥️ by
          <LandingLink class="underline" to="https://github.com/claudiabdm" external>
            <span class="text-red-800">
              claudiabdm , modified by walleeva2018 & Supported By WerHere
            </span>
          </LandingLink>
        </div>

      </section>
    </main>
    
  </div>
</template>

<style lang="postcss" scoped>
:root {
  --header-height: calc(104px + calc(1.97rem
        /* 31.52px */
        + 4.50 * var(--fluid-bp)));
}
</style>
