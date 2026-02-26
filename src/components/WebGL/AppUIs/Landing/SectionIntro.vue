<template>
  <section class="section-intro pb-20 -mt-16">
    <div class="container mx-auto px-4">
      <div class="flex flex-wrap">
        <div class="lg:pt-6 pt-6 w-full md:w-4/12 px-4 text-center" @mouseenter="$emit('play', 'Cheering While Sitting')">
          <div
            class="relative flex flex-col min-w-0 break-words glass-card w-full mb-8 rounded-lg intro-card"
          >
            <div class="px-4 py-5 flex-auto">
              <div
                class="intro-icon-badge intro-icon-amber text-white p-3 text-center inline-flex items-center justify-center w-12 h-12 mb-5 rounded-full"
              >
                <i class="fas fa-award"></i>
              </div>
              <h6 class="text-xl font-semibold" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 700;">All Coding Tutorials are Free</h6>
              <p class="mt-2 mb-4" style="color: var(--cosmos-text-muted);">
                I love learning tutorials from the internet for free. I would also like to give back to our community!
              </p>
            </div>
          </div>
        </div>

        <div class="w-full md:w-4/12 px-4 text-center" @mouseenter="$emit('play', 'Sitting Victory')">
          <div
            class="relative flex flex-col min-w-0 break-words glass-card w-full mb-8 rounded-lg intro-card"
          >
            <div class="px-4 py-5 flex-auto">
              <div
                class="intro-icon-badge intro-icon-brand text-white p-3 text-center inline-flex items-center justify-center w-12 h-12 mb-5 rounded-full"
              >
                <i class="fas fa-calendar-check"></i>
              </div>
              <h6 class="text-xl font-semibold" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 700;">From Easy to In-Depth</h6>
              <p class="mt-2 mb-4" style="color: var(--cosmos-text-muted);">
                It's only a matter of time that you will master the Web Platform Technology.
              </p>
            </div>
          </div>
        </div>

        <div class="lg:pt-6 w-full md:w-4/12 px-4 text-center" @mouseenter="$emit('play', 'Sitting Thumbs Up')">
          <div
            class="relative flex flex-col min-w-0 break-words glass-card w-full mb-8 rounded-lg intro-card"
          >
            <div class="px-4 py-5 flex-auto">
              <div
                class="intro-icon-badge intro-icon-emerald text-white p-3 text-center inline-flex items-center justify-center w-12 h-12 mb-5 rounded-full"
              >
                <i class="fas fa-fingerprint"></i>
              </div>
              <h6 class="text-xl font-semibold" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 700;">JavaScript Fantasy Land</h6>
              <p class="mt-2 mb-4" style="color: var(--cosmos-text-muted);">
                Nowadays, who doesn't love JavaScript?! It's in front end and backend server and desktop application such as electron and nwjs.
              </p>
            </div>
          </div>
        </div>
      </div>
      <div class="flex flex-wrap items-center mt-24">
        <div class="w-full md:w-5/12 px-4 mr-auto ml-auto">
          <div
            class="p-3 text-center inline-flex items-center justify-center w-16 h-16 mb-6 rounded-full"
            style="background: rgba(255,255,255,0.05); color: var(--cosmos-text-muted);"
          >
            <i class="fas fa-book-reader text-xl"></i>
          </div>
          <h3 class="text-3xl mb-2 font-semibold leading-normal" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 800;">
            Let's explore the possibilities within our Browser.
          </h3>
          <div
            class="text-lg font-light leading-relaxed mt-0 mb-4"
            style="color: var(--cosmos-text-muted);"
          >
            <div class="mb-3">
              Courses on Front End Technologies:
            </div>
            <ul class="course-list pl-0 list-none">
              <li class="course-list-item" v-for="(cr, cri) in courses" :key="cri" :style="{ '--course-color': courseColors[cri] || 'var(--cosmos-text-muted)' }">
                <span class="course-dot" :style="{ background: courseColors[cri] || 'var(--cosmos-text-muted)' }"></span>
                <span v-if="cr.underDevelopment" style="color: var(--cosmos-text-dim);">{{ cr.name }}  (In Progress)</span>
                <router-link class="course-link" :style="{ color: courseColors[cri] || 'var(--cosmos-text)' }" :to="`${cr.path}`" v-if="!cr.underDevelopment">{{ cr.name }}</router-link>
              </li>
            </ul>
          </div>
        </div>
        <div class="w-full md:w-4/12 px-4 mr-auto ml-auto">

          <div
            class="relative flex flex-col min-w-0 break-words w-full mb-6 rounded-lg overflow-hidden hero-card-pink"
          >
            <div class="w-full align-middle rounded-t-lg h-64">
              <GLArtCanvas class="h-full w-full">
                <Bloomer :settings="{
                  exposure: 1.0,
                  bloomStrength: 1.7,
                  bloomThreshold: 20.72 / 100.0,
                  bloomRadius: 72.99 / 100.0 * 2
                }"></Bloomer>

                <FastFlame :sx="3.6" :lowres="true"></FastFlame>
              </GLArtCanvas>
            </div>
            <blockquote class="relative p-8 mb-4">
              <h4 class="text-xl font-bold" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 700;">
                From Zero to Hero
              </h4>
              <p class="text-md font-light mt-2" style="color: rgba(255,255,255,0.7);">
                It's always intimidating to do what requires time and proper training. But with perseverance and every lesson on the journey, you are getting progress and closer and closer to your goal everyday.
              </p>
            </blockquote>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { courses } from '../../../../router'

export default {
  mixins: [
    require('../../Core/O3DVue').O3DVue
  ],
  data () {
    return {
      courses,
      courseColors: [
        '#f59e0b', // JS Basics - amber
        '#f97316', // ES6 - orange
        '#ef4444', // DOM - red
        '#ec4899', // Canvas 2D - pink
        '#8b5cf6', // WebGL - purple
        '#4371FF', // Three.js Basic - brand blue
        '#06b6d4', // Three.js Intermediate - cyan
        '#10b981', // Three.js Advanced - emerald
      ]
    }
  }
}
</script>

<style>
.section-intro {
  background-color: var(--cosmos-base);
  position: relative;
}
.section-intro::before {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100%;
  height: 400px;
  background: radial-gradient(ellipse at center top, rgba(245, 158, 11, 0.06) 0%, transparent 60%);
  pointer-events: none;
}

.intro-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.intro-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.3);
}

.intro-icon-badge {
  background: rgba(255, 255, 255, 0.06);
  position: relative;
}
.intro-icon-amber {
  color: var(--cosmos-amber);
  box-shadow: 0 0 20px rgba(245, 158, 11, 0.2);
}
.intro-icon-brand {
  color: var(--cosmos-brand);
  box-shadow: 0 0 20px rgba(67, 113, 255, 0.2);
}
.intro-icon-emerald {
  color: var(--cosmos-emerald);
  box-shadow: 0 0 20px rgba(16, 185, 129, 0.2);
}

.course-list-item {
  display: flex;
  align-items: center;
  padding: 6px 0;
}
.course-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 12px;
  flex-shrink: 0;
  box-shadow: 0 0 8px currentColor;
}
.course-link {
  text-decoration: none;
  transition: opacity 0.2s ease;
}
.course-link:hover {
  opacity: 0.8;
  text-decoration: underline;
}

.hero-card-pink {
  background: linear-gradient(135deg, rgba(236, 72, 153, 0.15) 0%, rgba(139, 92, 246, 0.15) 100%);
  border: 1px solid rgba(236, 72, 153, 0.2);
}
</style>
