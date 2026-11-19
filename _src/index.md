---
title: Home
layout: base.njk
---
{% include "navbar.html" %}

# Hello!
## Hey guys!
Welcome to my site.  
This page was made with **Eleventy** and written in Markdown.

[Go to Introduction](guide.html) 
[Here is my threejs](./three/index.html)

<is-land on:visible>

  <div id="counter" v-scope="{ count: 0 }">
    <p>Count: <span v-text="count"></span></p>
    <button @click="count++">Add one</button>
  </div>

  <template data-island>
    <script type="module">
      import { createApp } from '../js/petite-vue.es.js'
      createApp().mount('#counter')
    </script>
  </template>

</is-land>

<strong>Page last updated:</strong>
{% if gitLastCommit %}
  <time class="fmt-date" datetime="{{ gitLastCommit }}">{{ gitLastCommit }}</time>
{% else %}
  <em>not yet committed</em>
{% endif %}
&middot;
<strong>Site last built:</strong>
<time class="fmt-date" datetime="{{ build.timestamp }}">{{ build.timestamp }}</time>

<is-land on:visible>
  <template data-island>
    <script type="module">
      const fmt = new Intl.DateTimeFormat(undefined, {
        dateStyle: "medium",
        timeStyle: "short"
      });
      document.querySelectorAll("time.fmt-date").forEach((el) => {
        el.textContent = fmt.format(new Date(el.getAttribute("datetime")));
      });
    </script>
  </template>
</is-land>


