<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {
  }
}
</script>

<style>
:root {
  --cosmos-base: #0a0a0f;
  --cosmos-surface: rgba(255, 255, 255, 0.04);
  --cosmos-surface-border: rgba(255, 255, 255, 0.07);
  --cosmos-text: #f0f0f5;
  --cosmos-text-muted: #8888a0;
  --cosmos-text-dim: #555568;
  --cosmos-brand: #4371FF;
  --cosmos-amber: #f59e0b;
  --cosmos-pink: #ec4899;
  --cosmos-purple: #8b5cf6;
  --cosmos-cyan: #06b6d4;
  --cosmos-emerald: #10b981;
  --cosmos-red: #ef4444;
  --cosmos-orange: #f97316;
  --font-display: 'Syne', 'Inter', sans-serif;
}

#app {
  font-family: 'Inter', 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  line-height: 1.5;
  background-color: var(--cosmos-base);
  color: var(--cosmos-text);
}

.font-display {
  font-family: var(--font-display);
}

/* Glow utilities */
.glow-amber { box-shadow: 0 0 30px rgba(245, 158, 11, 0.15), 0 0 60px rgba(245, 158, 11, 0.05); }
.glow-pink { box-shadow: 0 0 30px rgba(236, 72, 153, 0.15), 0 0 60px rgba(236, 72, 153, 0.05); }
.glow-purple { box-shadow: 0 0 30px rgba(139, 92, 246, 0.15), 0 0 60px rgba(139, 92, 246, 0.05); }
.glow-cyan { box-shadow: 0 0 30px rgba(6, 182, 212, 0.15), 0 0 60px rgba(6, 182, 212, 0.05); }
.glow-emerald { box-shadow: 0 0 30px rgba(16, 185, 129, 0.15), 0 0 60px rgba(16, 185, 129, 0.05); }
.glow-brand { box-shadow: 0 0 30px rgba(67, 113, 255, 0.15), 0 0 60px rgba(67, 113, 255, 0.05); }

/* Glass card base */
.glass-card {
  background: var(--cosmos-surface);
  border: 1px solid var(--cosmos-surface-border);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
}

/* Gradient text utility */
.gradient-text {
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* Smooth section transitions */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(24px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-up {
  animation: fadeInUp 0.6s ease-out both;
}

/* Editor dark theme containers */
.editor-pane-dark {
  background-color: #1e1e1e;
  border-color: rgba(255, 255, 255, 0.06);
}

.editor-output-dark {
  background-color: #141419;
  color: var(--cosmos-text);
}

/* Override console output in JS editor for dark theme */
.editor-output-dark pre {
  color: var(--cosmos-text-muted);
}
.editor-output-dark pre.text-red-500 {
  color: var(--cosmos-red) !important;
}

/* Scrollbar styling for dark theme */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}
::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.02);
}
::-webkit-scrollbar-thumb {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 4px;
}
::-webkit-scrollbar-thumb:hover {
  background: rgba(255, 255, 255, 0.14);
}
</style>
