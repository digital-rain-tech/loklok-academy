<template>
  <div class="lesson-bar full overflow-scroll scrolling-touch relative">
    <router-link to="/course-catalogue" class="hover px-3 py-4 block text-center text-xs lesson-bar-back">
      <div class="inline-block loopsy">&larr; Back to Catalogue</div>
    </router-link>

    <div class="px-3 py-4 block text-xs lesson-bar-course-title text-center" v-if="lessons && lessons[0]">
      {{ lessons[0].meta.courseName }}
    </div>
    <router-link :to="`${lesson.path}`" exact-active-class="lesson-active" class="lesson-link px-3 py-4 block text-sm" v-for="(lesson, li) in lessons" :key="li">
      {{ pad(li + 1, 2) }} {{ lesson.name }}
    </router-link>
    <div class="padder" style="height: 300px;"></div>

    <router-link :to="nextCourse.path" style="width: 250px;" class="lesson-bar-next px-3 py-4 block text-xs text-center fixed left-0 w-full bottom-0 z-10" v-if="nextCourse">
      Up Next: {{ nextCourse.meta.courseName }}
    </router-link>
  </div>
</template>

<script>
import { courses } from '../../../../router'
import { O3DVue } from '../../Core/O3DVue'
export default {
  mixins: [
    O3DVue
  ],
  data () {
    let oneCourse = courses.find(c => c.meta.prefix === this.$route.meta.prefix)
    let currentCouseIdx = courses.findIndex(c => c.meta.prefix === this.$route.meta.prefix)
    let nextCourse = courses[currentCouseIdx + 1]
    let previousCourse = courses[currentCouseIdx - 1]
    let lessons = []
    if (oneCourse) {
      lessons = oneCourse.children.filter(e => !e.redirect)
        .map(e => {
          let newItem = JSON.parse(JSON.stringify(e))
          newItem.name = newItem.name.slice(3, newItem.name.length)
          return newItem
        })
    }
    return {
      previousCourse,
      nextCourse,
      lessons
    }
  },
  methods: {
    pad (n, width, z) {
      z = z || '0';
      n = n + '';
      return n.length >= width ? n : new Array(width - n.length + 1).join(z) + n;
    }
  }
}
</script>

<style lang="postcss">
@keyframes loopsy {
  0% {
    transform: translateX(200%);
  }
  100% {
    transform: translateX(-200%);
  }
}

.lesson-bar {
  background-color: #0d0d14;
  border-right: 1px solid rgba(255, 255, 255, 0.06);
}

.lesson-bar-back {
  background-color: rgba(255, 255, 255, 0.03);
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
  color: var(--cosmos-text-muted);
  transition: background-color 0.2s ease;
}
.lesson-bar-back:hover {
  background-color: rgba(255, 255, 255, 0.06);
}

.lesson-bar-course-title {
  background-color: rgba(255, 255, 255, 0.03);
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
  color: var(--cosmos-text);
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 0.75rem;
  letter-spacing: 0.05em;
}

.lesson-link {
  color: var(--cosmos-text-muted);
  border-bottom: 1px solid rgba(255, 255, 255, 0.04);
  transition: background-color 0.3s ease, color 0.3s ease;
}
.lesson-link:hover {
  background-color: rgba(255, 255, 255, 0.04);
  color: var(--cosmos-text);
}

.lesson-active {
  background: linear-gradient(90deg, rgba(6, 182, 212, 0.15) 0%, rgba(6, 182, 212, 0.05) 100%);
  color: var(--cosmos-cyan) !important;
  border-left: 3px solid var(--cosmos-cyan);
  box-shadow: inset 4px 0 12px rgba(6, 182, 212, 0.08);
}

.lesson-bar-next {
  background-color: #0d0d14;
  border-top: 1px solid rgba(255, 255, 255, 0.06);
  color: var(--cosmos-text-muted);
  transition: background-color 0.2s ease, color 0.2s ease;
}
.lesson-bar-next:hover {
  background-color: rgba(255, 255, 255, 0.04);
  color: var(--cosmos-text);
}

.hover:hover .loopsy{
  animation: loopsy 1s linear 0s infinite normal both;
}
.b-54{
  bottom: 54px;
}
</style>
