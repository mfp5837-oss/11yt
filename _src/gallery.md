---
title: gallery
layout: base.njk
---

<is-land on:visible>

<div id="gallery" v-scope="{ active: 'all' }">
  <div class="filters">
    <button @click="active = 'all'" :class="{ on: active === 'all' }" :aria-pressed="active === 'all'">All</button>
    <button @click="active = 'sketches'" :class="{ on: active === 'sketches' }" :aria-pressed="active === 'sketches'">Sketches</button>
    <button @click="active = 'photos'" :class="{ on: active === 'photos' }" :aria-pressed="active === 'photos'">Photos</button>
    <button @click="active = 'type'" :class="{ on: active === 'type' }" :aria-pressed="active === 'type'">Type</button>
  </div>
  <section class="topic" v-show="active === 'all' || active === 'sketches'">
    <h3>Sketches</h3>
    <img src="img/sketches/first.jpg" alt="Describe this image">
    <img src="img/sketches/second.jpg" alt="Describe this image">
  </section>
  <section class="topic" v-show="active === 'all' || active === 'photos'">
    <h3>Photos</h3>
    <img src="img/photos/first.jpg" alt="Describe this image">
    <img src="img/photos/second.jpg" alt="Describe this image">
  </section>
  <section class="topic" v-show="active === 'all' || active === 'type'">
    <h3>Type</h3>
    <img src="img/type/first.jpg" alt="Describe this image">
    <img src="img/type/second.jpg" alt="Describe this image">
  </section>
</div>

  <template data-island>
    <script type="module">
      import { createApp } from './js/petite-vue.js'
      createApp().mount('#gallery')
    </script>
  </template>

</is-land>