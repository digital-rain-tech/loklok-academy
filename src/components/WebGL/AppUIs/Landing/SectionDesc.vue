<template>
  <section class="section-desc relative py-20">
    <div
      class="bottom-auto top-0 left-0 right-0 w-full absolute pointer-events-none overflow-hidden -mt-20"
      style="height: 80px; transform: translateZ(0px);"
    >
      <svg
        class="absolute bottom-0 overflow-hidden"
        xmlns="http://www.w3.org/2000/svg"
        preserveAspectRatio="none"
        version="1.1"
        viewBox="0 0 2560 100"
        x="0"
        y="0"
      >
        <polygon
          fill="#0a0a0f"
          points="2560 0 2560 100 0 100"
        ></polygon>
      </svg>
    </div>
    <div class="container mx-auto px-4">
      <div class="items-center flex flex-wrap">
        <div class="w-full md:w-4/12 ml-auto mr-auto px-4">
          <GLArtCanvas class="h-full w-full progress-canvas-area rounded-lg" :rounded="'8px 8px 8px 8px'">
            <EnergyArt :pz="50" :lowres="true"></EnergyArt>
          </GLArtCanvas>
        </div>
        <div class="w-full md:w-5/12 ml-auto mr-auto px-4 pt-24 md:pt-0">
          <div class="md:pr-12">
            <div
              class="p-3 text-center inline-flex items-center justify-center w-16 h-16 mb-6 rounded-full"
              style="background: rgba(16, 185, 129, 0.1); color: var(--cosmos-emerald); box-shadow: 0 0 24px rgba(16, 185, 129, 0.15);"
            >
              <i class="fas fa-rocket text-xl"></i>
            </div>
            <h3 class="text-3xl font-semibold" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 800;">Progress over perfection.</h3>
            <p class="mt-4 text-lg leading-relaxed" style="color: var(--cosmos-text-muted);">
              Keep Trying, because heaven inspires you with your work.
            </p>
            <ul class="list-none mt-6">
              <li class="py-2">
                <div class="flex items-center">
                  <div>
                    <span
                      class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded-full mr-3"
                      style="background: rgba(16, 185, 129, 0.1); color: var(--cosmos-emerald);"
                      ><i class="fas fa-fingerprint"></i
                    ></span>
                  </div>
                  <div>
                    <h4 style="color: var(--cosmos-text-muted);">
                      Staring Coding. It can remove irrational fear.
                    </h4>
                  </div>
                </div>
              </li>
              <li class="py-2">
                <div class="flex items-center">
                  <div>
                    <span
                      class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded-full mr-3"
                      style="background: rgba(16, 185, 129, 0.1); color: var(--cosmos-emerald);"
                      ><i class="fab fa-html5"></i
                    ></span>
                  </div>
                  <div>
                    <h4 style="color: var(--cosmos-text-muted);">
                      Don't just read code online.
                    </h4>
                  </div>
                </div>
              </li>
              <li class="py-2">
                <div class="flex items-center">
                  <div>
                    <span
                      class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded-full mr-3"
                      style="background: rgba(16, 185, 129, 0.1); color: var(--cosmos-emerald);"
                      ><i class="far fa-paper-plane"></i
                    ></span>
                  </div>
                  <div>
                    <h4 style="color: var(--cosmos-text-muted);">
                      Type some Code by hand, not by copy and paste examples.
                    </h4>
                  </div>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { O3DVue } from '../../Core/O3DVue'
export default {
  mixins: [
    O3DVue
  ]
}
</script>

<style>
.section-desc {
  background-color: var(--cosmos-base);
  position: relative;
}
.section-desc::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  width: 50%;
  height: 80%;
  background: radial-gradient(ellipse at center left, rgba(16, 185, 129, 0.06) 0%, transparent 60%);
  pointer-events: none;
}
.progress-canvas-area{
  height: 500px;
  background-color: #0a0a0f;
  border: 1px solid rgba(255, 255, 255, 0.06);
}
</style>
