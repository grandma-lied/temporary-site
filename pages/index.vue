<template>
  <div>
    <section>
      <app-logo/>
    </section>

    <section class="important-section">
      <p class="1">Curiosity is the backbone of our studio. It pushes us to find new ways to animate, illustrate, write, and perpetually wonder if there's something missing that we can improve on.</p>

      <p class="2">Have we peaked your curiosity? Get in touch and let’s see what we can create together.</p>
    </section>
  </div>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  }
}
</script>

<style>
body {
  --bg: white;
  --bg-when-not-white: #eaf1e8;
  --gray1: #d9d6d3;
  --gray2: #a79f9d;
  --gray3: #5a5553;
  --gray4: #474342;
  --black: #333132;
  --ochre: #ba8537;
}

.intro {
  background-color: var(--black);
  color: var(--gray1);
  font-family: 'Lato', sans-serif;
  min-height: 100vh;
  padding: 4% 8% 8% 8%;
  width: 100%;
  font-size: 3em;
  line-height: 2;
}

.logo-image {
  width: 35%;
}

.important-section {
  background-color: var(--bg);
  display: grid;
  grid-gap: 5% 5%;
  grid-template-areas: ". .";
  grid-template-columns: 2fr 2fr 1fr;
  grid-template-rows: 1fr;
  height: 100%;
  padding: 7% 8% 15% 8%;
  width: 100%;
  font-size: 1.3em;
  line-height: 1.75;
}

.2 { grid-area: 2; }

.1 { grid-area: 1; }


</style>

