---
title: gallery
layout: base.njk
---

<is-land on:visible>

<div id="gallery" v-scope="{ active: 'all' }">
  <div class="filters">
    <button @click="active = 'all'" :class="{ on: active === 'all' }" :aria-pressed="active === 'all'">All</button>
    <button @click="active = 'sketches'" :class="{ on: active === 'sketches' }" :aria-pressed="active === 'sketches'">Animals</button>
    <button @click="active = 'photos'" :class="{ on: active === 'photos' }" :aria-pressed="active === 'photos'">Retro</button>
    <button @click="active = 'type'" :class="{ on: active === 'type' }" :aria-pressed="active === 'type'">Games</button>
  </div>
  <section class="topic" v-show="active === 'all' || active === 'sketches'">
    <h3>Animals</h3>
    <img src="./img/sketches/dog.jpg" alt="image of dog">
    <img src="./img/sketches/scarlet.jpg" alt="image of scralet Macaw">
  </section>
  <section class="topic" v-show="active === 'all' || active === 'photos'">
    <h3>Retro</h3>
    <img src="./img/photos/retro.jpg" alt="pic of two people playing on a retro console">
    <img src="./img/photos/console.jpg" alt="image of different reto consoles">
  </section>
  <section class="topic" v-show="active === 'all' || active === 'type'">
    <h3>Games</h3>
    <img src="./img/type/rtype.jpg" alt="image of the game R Type">
    <img src="./img/type/space.jpg" alt="image of space inavders">
  </section>
</div>

  <template data-island>
    <script type="module">
      import { createApp } from './js/petite-vue.js'
      createApp().mount('#gallery')
    </script>
  </template>

</is-land>