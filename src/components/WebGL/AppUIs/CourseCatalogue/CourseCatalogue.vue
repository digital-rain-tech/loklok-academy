<template>
  <div>
    <HeaderNav></HeaderNav>
    <div class="course-banner relative">
      <GLArtCanvas :rounded="'0px 0px 0px 0px'" class="full" bgcolor="#000000">
        <MBLinesBloom></MBLinesBloom>
        <Bloomer :settings="{
          exposure: 1.0,
          bloomStrength: 2,
          bloomThreshold: 10.72 / 100.0,
          bloomRadius: 50.99 / 100.0 * 2
        }"></Bloomer>
      </GLArtCanvas>
      <div class="absolute course-banner-overlay top-0 left-0 w-full h-full flex justify-center items-center">
        <div class="text-2xl lg:text-5xl" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 800; letter-spacing: -0.02em;">Course Catalogue</div>
      </div>
    </div>

    <section class="catalogue-section body-font max-w-5xl mx-auto">
      <div class="container px-5 py-24 mx-auto flex flex-wrap">
        <div class="flex flex-wrap w-full">
          <div class="md:w-1/2 lg:w-2/5 md:pr-10 md:py-6">
            <div class="flex relative pb-12" v-for="(course, ci) in courseList" :key="ci">
              <div v-if="ci < courseList.length - 1" class="h-full w-10 absolute inset-0 flex items-center justify-center">
                <div class="h-full w-1 pointer-events-none" style="background: rgba(255,255,255,0.06);"></div>
              </div>
              <div class="flex-shrink-0 w-10 h-10 rounded-full inline-flex items-center justify-center text-white relative z-10 course-step-dot"
                :style="{ background: course.color, boxShadow: '0 0 16px ' + course.color + '44' }">
                <i class="fa fa-asterisk text-xs"></i>
              </div>
              <div @click="() => $router.push(course.path)" class="flex-grow pl-4 cursor-pointer group">
                <h2 class="font-medium title-font text-sm mb-1 tracking-wider course-step-title" style="font-family: var(--font-display); font-weight: 700;">{{ course.name }}</h2>
                <p class="leading-relaxed" style="color: var(--cosmos-text-muted);">
                  {{ course.desc }}
                </p>
              </div>
            </div>
          </div>
          <div class="w-full md:w-1/2 lg:w-3/5 rounded-lg md:mt-0 mt-12">
            <div class="course-catalogue-art rounded-lg ">
              <GLArtCanvas v-if="!isSmall" class="h-full w-full rounded-lg" :rounded="'8px 8px 8px 8px'">
                <GLFlower></GLFlower>
              </GLArtCanvas>
            </div>
          </div>
        </div>
      </div>
    </section>
    <SectionFooter></SectionFooter>
  </div>
</template>

<script>
import { routes } from '../../../../router'
export default {
  mixins: [
    require('../../Core/O3DVue').O3DVue
  ],
  data () {
    return {
      isSmall: window.innerWidth < 500,
      jsbasics: routes.find(r => r.path === '/lessons/js-basics').children,
      courseList: [
        { name: 'JavaScript Basics', desc: 'Basic Logic and Code Organisation.', path: '/lessons/js-basics', color: '#f59e0b' },
        { name: 'ES6 Basics', desc: 'String Templates, Class, Arrow Functions.', path: '/lessons/es6-basics', color: '#f97316' },
        { name: 'DOM Basics', desc: 'Document Object Model is the Structure behind a Web page. In this unit, we will be learning about basic animation of a web page.', path: '/lessons/dom-basics', color: '#ef4444' },
        { name: 'Canvas 2D Basics', desc: 'We will learn about drawing basic shapes in 2D such as circles and lines.', path: '/lessons/canvas-2d-basics', color: '#8b5cf6' },
        { name: 'WebGL Raw API Basics', desc: 'We will learn about the journey of a particle from code to pixel on screen.', path: '/lessons/webgl-basics', color: '#10b981' },
        { name: 'THREE JS Basics', desc: 'We will be using THREE.JS to make some basic WebGL Rendering.', path: '/lessons/threejs-basics', color: '#ec4899' },
        { name: 'THREE JS Intermediate', desc: 'We will be using THREE.JS to make some basic Custom Shader WebGL.', path: '/lessons/threejs-intermediate', color: '#06b6d4' },
        { name: 'THREE JS Advanced', desc: 'We will be using THREE.JS to make some custom GPGPU WebGL ART.', path: '/lessons/threejs-advanced', color: '#4371FF' },
      ]
    }
  }
}
</script>

<style lang="postcss">
.course-banner{
  height: 55vh;
}

.course-banner-overlay{
  background: linear-gradient(180deg, rgba(10, 10, 15, 0) 0%, rgba(10, 10, 15, 0.6) 100%);
}

.catalogue-section {
  color: var(--cosmos-text-muted);
}

.course-step-title {
  color: var(--cosmos-text);
  transition: opacity 0.2s ease;
}
.group:hover .course-step-title {
  text-decoration: underline;
}

.course-step-dot {
  transition: transform 0.2s ease;
}
.group:hover .course-step-dot,
.flex:hover .course-step-dot {
  transform: scale(1.15);
}

.course-catalogue-art{
  position: sticky;
  top: 30px;
  height: 550px;
  background-color: #0a0a0f;
  border: 1px solid rgba(255, 255, 255, 0.06);
}
</style>
