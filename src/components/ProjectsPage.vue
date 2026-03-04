<script setup lang="ts">
import { Card, CardContent, CardFooter, CardHeader, CardTitle } from '@/components/ui/card';
import { Badge } from '@/components/ui/badge';
import { ExternalLink, Github, Code2, Users } from 'lucide-vue-next';

// Comprehensive Repo Data mapped directly from active contribution histories
const significantRepos = [
  {
    title: 'ds410-course-proj-redo',
    language: 'Python / Bash',
    role: 'Creator (60+ Commits)',
    description: 'Data Science scaling methodology project focused on robust testing infrastructures running through high-performance computing clusters (Roar).',
    contributions: 'Engineered extreme-scale testing scripts and standalone structural hotfixes deployed natively across supercomputing infrastructure.',
    url: 'https://github.com/RaameshB/ds410-course-proj-redo'
  },
  {
    title: 'EchoTorch',
    language: 'Python',
    role: 'Contributor',
    description: 'A robust Python toolkit for Reservoir Computing and Echo State Network experimentation, based entirely on PyTorch abstractions.',
    contributions: 'Served as an active contributor helping refine and test PyTorch-based Deep Reservoir Computing models and their network architectures.',
    url: 'https://github.com/RaameshB/EchoTorch'
  },
  {
    title: 'S-IDS4 / S-IDS4-torch',
    language: 'Python / Research',
    role: 'Creator (WIP)',
    description: 'An exploratory mathematical implementation actively mapping Sparse Input Dependent State Space Models (S4).',
    contributions: 'Currently writing and executing dynamic model experiments aimed at exploring sparse-input dependencies for state parameters.',
    url: 'https://github.com/RaameshB/S-IDS4'
  },
  {
    title: 'N-HiTS-Experiments',
    language: 'Python / Forecasting',
    role: 'Creator (WIP)',
    description: 'Experimentation pipeline and algorithmic scratchpad built to validate Neural Hierarchical Interpolation methods for time series forecasting.',
    contributions: 'Scaffolded tracking environments and ran structural benchmarks to observe predictive time-series scaling.',
    url: 'https://github.com/RaameshB/N-HiTS-Experiments'
  },
  {
    title: 'LogDepth-SSM',
    language: 'Jupyter',
    role: 'Creator (WIP)',
    description: 'Exploratory data analysis utilizing State Space Models (SSMs) to map and interpret Log Depth dynamics in geological or software streams.',
    contributions: 'Initiated the deep feature mapping pipelines and built the mathematical state interaction modeling baseline.',
    url: 'https://github.com/RaameshB/LogDepth-SSM'
  },
  {
    title: 'c0mpiled-psu',
    language: 'Backend Architecture',
    role: 'Backend Developer / Contributor',
    description: 'Server-side application logic and data architecture supporting platform systems for the c0mpiled open-source organization at PSU.',
    contributions: 'Architected backend services, managing application logic, integrations, and core workflows for organizational resources.',
    url: 'https://github.com/RaameshB/c0mpiled-psu'
  },
  {
    title: 'Temporal-Fusion-Transformer',
    language: 'Python / Forecasting',
    role: 'Creator',
    description: 'An experimental ML playground targeting the Temporal Fusion Transformer (TFT) architecture for complex multi-horizon forecasting.',
    contributions: 'Bootstrapped the initial setup and began structuring the multi-variate modeling constraints and time-series bindings.',
    url: 'https://github.com/RaameshB/Temporal-Fusion-Transformer'
  },
  {
    title: 'Task Prioritization App',
    language: 'Web Stack',
    role: 'Creator',
    description: 'An interactive productivity and tracking tool built to process and prioritize daily workloads dynamically based on collegiate deadlines.',
    contributions: 'Engineered the original baseline tracking functionality and structural view architecture for algorithmic task organization.',
    url: 'https://github.com/RaameshB/getting-back-on-track-with-school---task-prioritization-app'
  }
];
</script>

<template>
  <div class="pt-32 pb-16 px-6 relative overflow-hidden max-w-5xl mx-auto z-10 animate-in fade-in slide-in-from-bottom-4 duration-700">
    <div class="flex items-center gap-4 mb-4">
      <Github class="w-10 h-10 text-indigo-400" />
      <h1 class="text-4xl md:text-5xl font-extrabold tracking-tight text-slate-100">Repositories</h1>
    </div>
    <p class="text-xl text-slate-400 max-w-2xl mb-12 font-light">
      A vetted outline of my most active academic benchmarks, experimental model architectures, and open-source contributions.
    </p>

    <div class="grid grid-cols-1 gap-8">
      <Card 
        v-for="repo in significantRepos" 
        :key="repo.title" 
        class="bg-slate-900/40 border-slate-800/60 hover:border-indigo-500/50 transition-colors backdrop-blur-md rounded-2xl overflow-hidden"
      >
        <CardHeader class="pb-4 border-b border-slate-800/40 bg-slate-900/30">
          <div class="flex justify-between items-start">
            <div class="space-y-2">
              <CardTitle class="text-2xl font-bold text-slate-100 flex items-center gap-3">
                {{ repo.title }}
              </CardTitle>
              <Badge variant="secondary" class="bg-indigo-500/10 text-indigo-300 border border-indigo-500/30 shadow-sm shadow-indigo-500/10">
                <Users class="w-3 h-3 mr-1.5 inline" />
                {{ repo.role }}
              </Badge>
            </div>
            <a :href="repo.url" target="_blank" class="p-2 hover:bg-slate-800 rounded-full transition-colors group">
              <ExternalLink class="w-6 h-6 text-slate-400 group-hover:text-white" />
            </a>
          </div>
        </CardHeader>
        <CardContent class="pt-6">
          <h4 class="text-slate-200 font-semibold mb-2">About the Project</h4>
          <p class="text-slate-400 text-base leading-relaxed mb-6">{{ repo.description }}</p>
          
          <h4 class="text-slate-200 font-semibold mb-2">My Actual Contributions</h4>
          <ul class="list-disc list-inside text-slate-400 space-y-1">
            <li>{{ repo.contributions }}</li>
          </ul>
        </CardContent>
        <CardFooter class="pt-4 pb-6 bg-slate-950/20 border-t border-slate-800/20">
          <div class="flex items-center gap-2 text-slate-500 text-sm font-medium">
            <Code2 class="w-4 h-4 text-slate-600" />
            Primary Stack: {{ repo.language }}
          </div>
        </CardFooter>
      </Card>
    </div>
  </div>
</template>
