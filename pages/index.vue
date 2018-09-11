<template>
  <div>
    <section>
      <app-logo/>
    </section>

    <section class="important-section">
      <p class="1">Curiosity is the backbone of our studio. It pushes us to find new ways to animate, illustrate, write, and perpetually wonder if there's something missing that we can improve on.</p>

      <div class="2">Have we peaked your curiosity? Get in touch and let’s see what we can create together. <br>
        <div class="whut">
          <svg xmlns="http://www.w3.org/2000/svg" version="1.1" class="goo">
            <defs>
              <filter id="goo">
                <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
                <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -9" result="goo" />
                <feComposite in="SourceGraphic" in2="goo"/>
              </filter>
            </defs>
          </svg>

          <span class="button--bubble__container">
            <a href="mailto:helen.v.holmes@gmail.com" class="button button--bubble">
              Contact Us
            </a>
            <span class="button--bubble__effect-container">
              <span class="circle top-left"></span>
              <span class="circle top-left"></span>
              <span class="circle top-left"></span>

              <span class="button effect-button"></span>

              <span class="circle bottom-right"></span>
              <span class="circle bottom-right"></span>
              <span class="circle bottom-right"></span>
            </span>
          </span>
        </div>
      </div>
    </section>

    <footer class="footer">
        <img src="~/assets/img/logo.png" alt="Your Grandma Lied logo" class="logo-footer">
    </footer>
  </div>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  },
  async mounted () {
    return {
      link: [
        { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css?family=Roboto' }
      ],
      script: [
        { src: 'https://cdnjs.cloudflare.com/ajax/libs/gsap/1.17.0/plugins/CSSPlugin.min.js' },
        { src: 'https://cdnjs.cloudflare.com/ajax/libs/gsap/1.17.0/easing/EasePack.min.js' },
        { src: 'https://cdnjs.cloudflare.com/ajax/libs/gsap/1.17.0/TweenLite.min.js' },
        { src: 'https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js' },
        { src: 'https://cdnjs.cloudflare.com/ajax/libs/gsap/latest/TimelineLite.min.js' }
      ],
      plugins: ['~/plugins/button']
    } 
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

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

.logo-footer {
  width: 10%;
}

.important-section {
  background-color: var(--bg);
  display: grid;
  grid-gap: 5% 5%;
  grid-template-areas: ". .";
  grid-template-columns: 2fr 2fr 0.5fr;
  grid-template-rows: 1fr;
  height: 100%;
  padding: 7% 8% 5% 8%;
  width: 100%;
  font-size: 1.3em;
  line-height: 1.75;
}

.2 { grid-area: 2; }

.1 { grid-area: 1; }

.footer {
  align-items: center;
  display: flex;
  justify-content: center;
  text-align: center;
  padding: 4% 0 8% 0;
}

.whut {
  display: block;
  height: 100%;
  animation: hue-rotate 10s linear infinite;
  margin-top: -25px;
}

.button {
  -webkit-font-smoothing: antialiased;
  background-color: #222;
  border: none;
  color: var(--white);
  display: inline-block;
  padding: 20px 60px;
  text-decoration: none;
  transition: all 0.1s ease-out;
  user-select: none;
}
.button:hover {
  background-color: #90feb5;
  color: #fff;
}
.button:active {
  transform: scale(0.95);
}
.button--bubble {
  position: relative;
  z-index: 2;
  color: white;
  background: none;
}
.button--bubble:hover {
  background: none;
}
.button--bubble:hover + .button--bubble__effect-container .circle {
  background: #44fd82;
}
.button--bubble:hover + .button--bubble__effect-container .button {
  background: #44fd82;
}
.button--bubble:active + .button--bubble__effect-container {
  transform: scale(0.95);
}
.button--bubble__container {
  position: relative;
  display: inline-block;
}
.button--bubble__container .effect-button {
  position: absolute;
  width: 50%;
  height: 25%;
  top: 50%;
  left: 25%;
  z-index: 1;
  transform: translateY(-50%);
  background: #222;
  transition: background 0.1s ease-out;
}
.button--bubble__effect-container {
  position: absolute;
  display: block;
  width: 200%;
  height: 400%;
  top: -150%;
  left: -50%; 
  -webkit-filter: url("#goo");
  filter: url("#goo");
  transition: all 0.1s ease-out;
  pointer-events: none;
}
.button--bubble__effect-container .circle {
  position: absolute;
  width: 25px;
  height: 25px;
  border-radius: 15px;
  background: #222;
  transition: background 0.1s ease-out;
}
.button--bubble__effect-container .circle.top-left {
  top: 40%;
  left: 27%;
}
.button--bubble__effect-container .circle.bottom-right {
  bottom: 40%;
  right: 27%;
}
.goo {
  position: absolute;
  visibility: hidden;
  width: 1px;
  height: 1px;
}

.button--bubble__container {
  top: 50%;
  margin-top: -25px;
}

@keyframes hue-rotate {
  from {
    -webkit-filter: hue-rotate(0);
    -moz-filter: hue-rotate(0);
    -ms-filter: hue-rotate(0);
    filter: hue-rotate(0);
  }
  to {
    -webkit-filter: hue-rotate(360deg);
    -moz-filter: hue-rotate(360deg);
    -ms-filter: hue-rotate(360deg);
    filter: hue-rotate(360deg);
  }
}

</style>

