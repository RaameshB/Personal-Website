<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue';
import { Github, Linkedin, Mail, Code2, ExternalLink, Twitter, Gitlab } from 'lucide-vue-next';
import { Button } from '@/components/ui/button';
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from '@/components/ui/card';
import { Badge } from '@/components/ui/badge';
import ProjectsPage from '@/components/ProjectsPage.vue';

const currentPath = ref(window.location.hash)

const updatePath = () => {
  currentPath.value = window.location.hash
}

onMounted(() => {
  window.addEventListener('hashchange', updatePath)
})

onUnmounted(() => {
  window.removeEventListener('hashchange', updatePath)
})

const isHome = computed(() => {
  return currentPath.value === '' || currentPath.value === '#/'
})

const projects = [
  {
    title: 'ds410-course-proj-redo',
    description: 'Data Science scaling methodology project focused on robust testing infrastructures running through high-performance computing networks.',
    tags: ['Python', 'HPC Clusters', 'Data Science'],
    url: 'https://github.com/RaameshB/ds410-course-proj-redo'
  },
  {
    title: 'EchoTorch',
    description: 'A robust Python toolkit for Reservoir Computing and Echo State Network experimentation natively based on PyTorch.',
    tags: ['Python', 'PyTorch', 'Research Contributor'],
    url: 'https://github.com/RaameshB/EchoTorch'
  },
  {
    title: 'S-IDS4',
    description: 'Exploratory mathematical modeling mapping Sparse Input Dependent State Space Models (S4).',
    tags: ['Machine Learning', 'SSMs (WIP)'],
    url: 'https://github.com/RaameshB/S-IDS4'
  },
  {
    title: 'N-HiTS-Experiments',
    description: 'Experimentation tracking pipeline built to validate Neural Hierarchical Interpolation for time series forecasting.',
    tags: ['Python', 'Time Series (WIP)'],
    url: 'https://github.com/RaameshB/N-HiTS-Experiments'
  }
];
</script>

<template>
  <div class="min-h-screen bg-slate-950 text-slate-50 selection:bg-indigo-500/30 font-sans cursor-default transition-colors duration-500">
    <!-- Navbar / Header -->
    <header class="fixed top-0 w-full z-50 backdrop-blur-xl bg-slate-950/60 border-b border-slate-800/50">
      <div class="max-w-5xl mx-auto px-6 h-16 flex items-center justify-between">
        <a href="#/" class="font-bold text-xl md:text-2xl tracking-tight bg-gradient-to-r from-white to-slate-400 bg-clip-text text-transparent hover:opacity-80 transition-opacity">
          RB.
        </a>
        <nav class="flex items-center gap-4 sm:gap-6">
          <a href="#/" class="text-sm font-semibold transition-colors hidden sm:block" :class="{ 'text-indigo-400': isHome, 'text-slate-300 hover:text-white': !isHome }">Home</a>
          <a href="#/repos" class="text-sm font-semibold transition-colors mr-1 sm:mr-3 border-r border-slate-700/50 pr-4 sm:pr-8" :class="{ 'text-indigo-400': currentPath === '#/repos', 'text-slate-300 hover:text-white': currentPath !== '#/repos' }">Repos</a>
          
          <a href="https://github.com/RaameshB" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-indigo-400 transition-colors">
            <Github class="w-5 h-5 sm:w-6 sm:h-6" />
          </a>
          <a href="https://gitlab.com/RaameshB" title="GitLab Profile" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-indigo-400 transition-colors">
            <Gitlab class="w-5 h-5 sm:w-6 sm:h-6" />
          </a>
          <a href="https://www.linkedin.com/in/raameshbala/" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-indigo-400 transition-colors">
            <Linkedin class="w-5 h-5 sm:w-6 sm:h-6" />
          </a>
          <a href="https://twitter.com/raameshb_" target="_blank" rel="noopener noreferrer" class="text-slate-400 hover:text-indigo-400 transition-colors">
            <Twitter class="w-5 h-5 sm:w-6 sm:h-6" />
          </a>
        </nav>
      </div>
    </header>

    <div v-if="isHome">
      <!-- Hero Section -->
      <main class="pt-32 pb-16 relative overflow-hidden">
        <!-- Glow effect -->
        <div class="absolute top-0 left-1/4 w-96 h-96 bg-indigo-600/20 rounded-full blur-[128px] pointer-events-none"></div>
        <div class="absolute top-20 right-1/4 w-72 h-72 bg-cyan-600/10 rounded-full blur-[96px] pointer-events-none"></div>

        <div class="max-w-5xl mx-auto px-6 relative z-10 flex flex-col items-start pt-16 pb-20 animate-in fade-in slide-in-from-bottom-8 duration-1000">
          <Badge variant="outline" class="mb-6 border-indigo-500/30 text-indigo-300 bg-indigo-500/10 px-4 py-1.5 text-sm font-medium tracking-wide rounded-full shadow-[0_0_15px_rgba(99,102,241,0.2)]">
            Student ML Researcher
          </Badge>
          
          <h1 class="text-5xl md:text-7xl font-extrabold tracking-tight mb-6 leading-[1.1] max-w-4xl">
            Hi, I'm <span class="bg-gradient-to-r from-indigo-400 via-purple-400 to-cyan-400 bg-clip-text text-transparent drop-shadow-sm">Raamesh</span>.
          </h1>
          
          <p class="text-xl md:text-2xl text-slate-400 max-w-3xl mb-12 leading-relaxed font-light">
            Just a random dude who codes stuff sometimes. Exploring machine learning, building beautiful interfaces, and engineering robust systems.
          </p>
          
          <div class="flex flex-col sm:flex-row gap-5 w-full sm:w-auto">
            <Button size="lg" class="bg-indigo-600 text-white hover:bg-indigo-500 hover:shadow-[0_0_20px_rgba(99,102,241,0.4)] h-14 px-8 text-base font-semibold rounded-full group transition-all w-full sm:w-auto">
              <a href="https://www.linkedin.com/in/raameshbala/" target="_blank" class="flex items-center">
                <Mail class="w-5 h-5 mr-2 group-hover:scale-110 transition-transform" />
                Let's Connect
              </a>
            </Button>
            <Button size="lg" variant="outline" class="border-slate-700 text-slate-300 hover:bg-slate-800/80 hover:text-white h-14 px-8 text-base font-medium rounded-full bg-slate-900/50 backdrop-blur transition-all w-full sm:w-auto">
              <a href="#/repos" class="flex items-center">
                <Code2 class="w-5 h-5 mr-2" />
                View Repos
              </a>
            </Button>
          </div>
        </div>

        <!-- Projects Section -->
        <div class="max-w-5xl mx-auto px-6 mt-24 relative z-10">
          <div class="flex items-center gap-3 mb-10">
            <Code2 class="w-8 h-8 text-indigo-400" />
            <h2 class="text-4xl font-bold tracking-tight text-slate-100">Featured Projects</h2>
          </div>
          
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
            <Card 
              v-for="project in projects" 
              :key="project.title" 
              class="bg-slate-900/40 border-slate-800/60 hover:border-indigo-500/50 hover:bg-slate-800/40 hover:-translate-y-1 hover:shadow-2xl hover:shadow-indigo-500/10 transition-all duration-300 backdrop-blur-md group flex flex-col rounded-2xl overflow-hidden"
            >
              <CardHeader class="pb-3">
                <CardTitle class="text-2xl font-bold flex items-center justify-between text-slate-100 group-hover:text-indigo-400 transition-colors">
                  {{ project.title }}
                  <a :href="project.url" target="_blank" class="opacity-0 group-hover:opacity-100 transition-opacity p-2 hover:bg-slate-800 rounded-full">
                     <ExternalLink class="w-5 h-5 text-slate-300 hover:text-white" />
                  </a>
                </CardTitle>
              </CardHeader>
              <CardContent class="flex-grow pb-6">
                <CardDescription class="text-slate-400 text-base leading-relaxed">
                  {{ project.description }}
                </CardDescription>
              </CardContent>
              <CardFooter class="flex flex-wrap gap-2 pt-0 pb-6">
                <Badge 
                  v-for="tag in project.tags" 
                  :key="tag" 
                  variant="secondary" 
                  class="bg-slate-950/50 border border-slate-800 hover:bg-slate-800 text-indigo-300 px-3 py-1 font-medium rounded-md"
                >
                  {{ tag }}
                </Badge>
              </CardFooter>
            </Card>
          </div>
        </div>
      </main>
    </div>

    <!-- Router Logic (Projects Page) -->
    <div v-else-if="currentPath === '#/repos'">
      <ProjectsPage />
    </div>
    
    <footer class="border-t border-slate-800/50 mt-20 py-10 text-center text-slate-500 w-full relative z-10 bg-slate-950/80 backdrop-blur-lg">
      <p class="text-sm font-medium">© {{ new Date().getFullYear() }} Raamesh Bala. Built with Vue & shadcn-vue.</p>
    </footer>
  </div>
</template>

<style>
* {
  font-family: 'Inter', sans-serif;
}
body {
  margin: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
