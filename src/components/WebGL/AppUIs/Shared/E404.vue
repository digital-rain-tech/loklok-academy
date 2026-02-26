<template>
  <div>
    <HeaderNav></HeaderNav>
    <div class="course-banner relative">
      <GLArtCanvas :rounded="'0px 0px 0px 0px'" class="full" bgcolor="#000000">
        <Bloomer :settings="{
          exposure: 1.0,
          bloomStrength: 2,
          bloomThreshold: 10.72 / 100.0,
          bloomRadius: 50.99 / 100.0 * 2
        }"></Bloomer>
        <FastFlame :sx="3.6"></FastFlame>
      </GLArtCanvas>
      <div class="absolute e404-overlay top-0 left-0 w-full h-full flex flex-col justify-center items-center">
        <div class="text-2xl lg:text-4xl" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 800;">Not Found</div>
        <div class="text-xl lg:text-3xl my-2" style="color: var(--cosmos-text-dim);">or</div>
        <div class="text-2xl lg:text-4xl" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 800;">Under Development</div>
        <div class="mt-12 cursor-pointer e404-back-link" @click="$router.go(-1)">&larr; Let's Go Back</div>
      </div>
    </div>

    <section class="max-w-5xl mx-auto">
      <div class="container px-5 py-24 mx-auto flex flex-wrap">
        <div class="flex flex-wrap w-full">
          <div class="w-full rounded-lg md:mt-0 mt-12">
            <div class="e404-art rounded-lg ">
              <GLArtCanvas class="h-full w-full rounded-lg" :rounded="'8px 8px 8px 8px'">
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
      jsbasics: routes.find(r => r.path === '/lessons/js-basics').children
    }
  }
}
</script>

<style lang="postcss">
.e404-overlay {
  background: linear-gradient(180deg, rgba(10, 10, 15, 0) 0%, rgba(10, 10, 15, 0.5) 100%);
}

.e404-back-link {
  color: var(--cosmos-brand);
  transition: opacity 0.2s ease;
  text-decoration: underline;
}
.e404-back-link:hover {
  opacity: 0.8;
}

.e404-art {
  position: sticky;
  top: 30px;
  height: 550px;
  background-color: #0a0a0f;
  border: 1px solid rgba(255, 255, 255, 0.06);
}
</style>
