<template>
  <section class="section-cta relative pb-24 pt-12">
    <div class="container mx-auto px-4">
      <div class="items-center flex flex-wrap justify-center">
        <div class="w-full md:w-5/12 px-4 text-center inline-block">
          <router-link
            to="/course-catalogue"
            class="cta-card relative cursor-pointer flex flex-col min-w-0 break-words w-full mb-8 rounded-lg"
          >
            <div class="px-6 py-8 flex-auto">
              <div
                class="p-3 text-center inline-flex items-center justify-center w-14 h-14 mb-5 rounded-full"
                style="background: rgba(245, 158, 11, 0.1); color: var(--cosmos-amber); box-shadow: 0 0 24px rgba(245, 158, 11, 0.15);"
              >
                <i class="fas fa-icons text-lg"></i>
              </div>
              <h6 class="text-2xl font-semibold" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 800;">View Course Catalogue</h6>
              <p class="mt-3 mb-4" style="color: var(--cosmos-text-muted);">
                Let's begin your journey of developing your dream web app today.
              </p>
              <span class="cta-button inline-block mt-2 px-6 py-2 rounded-full text-sm font-semibold">
                Explore Courses &rarr;
              </span>
            </div>
          </router-link>
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
.section-cta {
  background-color: var(--cosmos-base);
}

.cta-card {
  background: linear-gradient(135deg, rgba(245, 158, 11, 0.06) 0%, rgba(236, 72, 153, 0.06) 100%);
  border: 1px solid rgba(245, 158, 11, 0.12);
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
  text-decoration: none;
}
.cta-card:hover {
  transform: translateY(-4px);
  border-color: rgba(245, 158, 11, 0.25);
  box-shadow: 0 8px 40px rgba(245, 158, 11, 0.08), 0 0 60px rgba(236, 72, 153, 0.04);
}

.cta-button {
  background: linear-gradient(135deg, var(--cosmos-amber), var(--cosmos-pink));
  color: white;
  transition: opacity 0.2s ease, transform 0.2s ease;
}
.cta-card:hover .cta-button {
  opacity: 0.9;
  transform: translateX(4px);
}
</style>
