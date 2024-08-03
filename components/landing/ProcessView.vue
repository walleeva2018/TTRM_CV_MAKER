<template>
  <div class="video-container">
    <h2 class="video-heading">Who Are We?</h2>

    <iframe width="560" height="315" src="https://www.youtube.com/embed/22bdbn276t8?si=emXQEMshn1bbrlEg"
      title="YouTube video player" frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

  </div>
  <div class="video-container">
    <h2 class="video-heading">How This Site Works</h2>

    <iframe width="560" height="315" src="https://www.youtube.com/embed/XkumGvWzCQc?si=xUCJe-og1VJ9gvhr"
      title="YouTube video player" frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
.video-container {
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin: 0 auto;
}

.video-heading {
  font-size: 1.5em;
  margin-bottom: 20px;
  text-align: center;
}

.iframe-container {
  position: relative;
  padding-bottom: 56.25%;
  /* 16:9 aspect ratio */
  height: 0;
  overflow: hidden;
  max-width: 100%;
  background: #000;
}

.iframe-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 0;
}
</style>