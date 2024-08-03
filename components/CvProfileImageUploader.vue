<script setup lang="ts">
const emit = defineEmits<{
  (event: 'update:modelValue', value: string | null | undefined): void
}>()

const isPhotoLoading = ref(false)

async function uploadImage(e: Event) {
  isPhotoLoading.value = true
  const file = (e.target as HTMLInputElement).files?.[0]
  if (file) {
    const readerResult = await fileToDataUri(file)
    const imageDataUri = await resizeImageFromReader(readerResult)
    emit('update:modelValue', imageDataUri)
    isPhotoLoading.value = false
  }
}

function clearProfileImage() {
  emit('update:modelValue', null)
  isPhotoLoading.value = false
}

function fileToDataUri(blob: Blob) {
  return new Promise<string>((resolve, reject) => {
    const reader = new FileReader()
    reader.readAsDataURL(blob)

    reader.addEventListener(
      'load',
      (e) => {
        const readerResult = e.target?.result
        if (typeof readerResult === 'string')
          resolve(readerResult)
        else
          reject(new Error('Something went wrong'))
      },
      { once: true },
    )
  })
}

function resizeImageFromReader(readerResult: string) {
  const img = new Image()
  img.src = readerResult
  return new Promise<string>(resolve =>
    img.addEventListener(
      'load',
      () => {
        const resizedImage = resizeImage(img)
        resolve(resizedImage)
      },
      { once: true },
    ),
  )
}

function resizeImage(imgToResize: HTMLImageElement, resizingFactor = 0.25) {
  const canvas = document.createElement('canvas')
  const context = canvas.getContext('2d')

  const originalWidth = imgToResize.width
  const originalHeight = imgToResize.height

  const canvasWidth = originalWidth * resizingFactor
  const canvasHeight = originalHeight * resizingFactor

  canvas.width = canvasWidth
  canvas.height = canvasHeight

  if (context)
    context.drawImage(imgToResize, 0, 0, canvasWidth, canvasHeight)

  return canvas.toDataURL()
}
</script>

<template>
  <div class="flex-col lg:flex-row">
    <div class="video-container">
      <h2 class="video-heading">What Personal Information Are Needed</h2>
      <div class="iframe-container">
        <iframe src="https://www.youtube.com/embed/XkumGvWzCQc?si=xUCJe-og1VJ9gvhr"
          title="YouTube video player" frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
      </div>
    </div>
    <div class="upload-buttons">
      <label
        tabindex="0"
        for="profile-image-uploader"
        class="form__btn basis-full"
      >
        {{ isPhotoLoading ? "Loading..." : $t("upload-profile-image") }}
        <input
          id="profile-image-uploader"
          type="file"
          accept="image/*"
          name="uploadProfileImage"
          class="hidden"
          @change="uploadImage"
        >
      </label>
      <button
        class="form__btn flex flex-col justify-center"
        type="button"
        @click="clearProfileImage"
      >
        {{ $t("clear-profile-image") }}
      </button>
    </div>
  </div>
</template>


<style scoped>
.flex {
  display: flex;
  flex-wrap: wrap;
}

.video-container {
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  max-width: 100%;
  margin: 0 auto 20px auto;
  flex: 1;
}

.video-heading {
  font-size: 1.5em;
  margin-bottom: 20px;
  text-align: center;
}

.iframe-container {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%;
  /* 16:9 aspect ratio */
  height: 0;
  overflow: hidden;
}

.iframe-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 0;
}

.upload-buttons {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  flex: 1;
}

.form__btn {
  margin: 10px 0;
}
</style>

