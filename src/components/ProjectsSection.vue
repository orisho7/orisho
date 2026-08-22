<template>
  <section class="section projects-section" aria-labelledby="projects-heading">
    <div class="section-content">
      <span class="section-eyebrow">Selected Work</span>
      <h2 id="projects-heading">Projects</h2>

      <div class="section-scroll">
        <ul class="project-list" role="list">
          <li v-for="(project, i) in projects" :key="project.title" class="project-item">
            <div class="project-header">
              <div class="project-title-row">
                <h3 class="project-name">{{ project.title }}</h3>
                <div class="project-meta">
                  <a
                    v-if="project.link"
                    :href="project.link"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="project-link"
                    :aria-label="`View ${project.title} live`"
                  >Live ↗</a>
                  <span v-if="project.year" class="project-year">{{ project.year }}</span>
                </div>
              </div>
              <ul class="project-bullets">
                <li v-for="bullet in project.bullets" :key="bullet">{{ bullet }}</li>
              </ul>
              <div class="project-tags">
                <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
              </div>
            </div>
            <div class="divider" />
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Rush',
    year: '2026',
    link: 'https://rush-page.vercel.app/',
    bullets: [
      'High-Performance Dependency Orchestrator built with Go and filesystem-level symlinks.',
      'Reduced dependency deployment time from ~2.5 minutes to 1 ms through intelligent caching and symlinks.',
      'Designed deterministic dependency resolution and efficient execution of build tasks while eliminating redundant operations.',
    ],
    tags: ['Go', 'Symlinks', 'Caching', 'CLI'],
  },
  {
    title: 'Robin',
    year: '2026',
    link: 'https://github.com/orisho7/Robin_CLI',
    bullets: [
      'Real-Time Observability Agent and CLI dashboard streaming live system metrics through Server-Sent Events (SSE).',
      'Continuous monitoring of CPU, memory, and system resources with low-overhead metric collection.',
      'Designed an interactive terminal-based dashboard with Bubble Tea for real-time system observability.',
    ],
    tags: ['Go', 'OS', 'SSE', 'Bubble Tea', 'TUI'],
  },
  {
    title: 'Radian',
    year: '2026',
    bullets: [
      'Engine Oil Recommendation Engine evaluating vehicle and engine specifications against manufacturer guidelines and Saudi Arabia’s climate and severe-driving conditions.',
      'Exposed via gRPC/HTTP and integrated with a multi-source vehicle and oil specification data pipeline.',
      'Implemented rule-based recommendation logic covering viscosity, engine type, climate, and severe-duty operating conditions.',
    ],
    tags: ['Go', 'Redis', 'gRPC', 'HTTP', 'Python', 'NestJS'],
  },
  {
    title: 'AI-Assisted Goal Management System',
    year: '2025',
    bullets: [
      'Behavioral Goal Tracking Platform built with Flutter, Node.js, Go, and MongoDB.',
      'Architected a scalable three-tier system with clear service boundaries for AI orchestration, product logic, and MongoDB persistence.',
      'Designed structured behavioral data flows to support long-term analysis and personalized insights.',
    ],
    tags: ['Flutter', 'Node.js', 'Go', 'MongoDB', 'AI'],
  },
  {
    title: 'VoiceMemo',
    year: '2025',
    link: 'https://github.com/orisho7/Mic',
    bullets: [
      'Audio Recording and Speech-to-Text Utility built with C#, Vosk, and NAudio.',
      'Engineered custom circular waveform visualizers and real-time volume indicators for interactive audio monitoring.',
      'Implemented configurable sample rates, recording timers, persistent settings, and structured error handling.',
    ],
    tags: ['C#', 'Vosk', 'NAudio', 'Audio Processing'],
  },
]
</script>

<style scoped>
.projects-section {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 var(--section-padding);
}

.project-list {
  list-style: none;
  display: flex;
  flex-direction: column;
}

.project-item {
  display: flex;
  flex-direction: column;
}

.project-header {
  display: flex;
  flex-direction: column;
  gap: 0.55rem;
  padding: 1.1rem 0;
}

.project-title-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}

.project-meta {
  display: flex;
  align-items: center;
  gap: 0.85rem;
  flex-shrink: 0;
}

.project-link {
  font-family: var(--font-mono);
  font-size: 0.62rem;
  font-weight: 500;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--color-text-secondary);
  text-decoration: none;
  border: 1px solid var(--color-border);
  padding: 0.35rem 0.8rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.3rem;
  transition: all 0.25s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  /* crisp pixel-like cursor */
  cursor: pointer;
}

.project-link:hover {
  color: var(--color-bg);
  background: var(--color-text-primary);
  border-color: var(--color-text-primary);
  transform: translateY(-1px);
}

.project-link:active {
  transform: translateY(0);
}

.project-name {
  font-family: var(--font-display);
  font-size: 0.82rem;
  font-weight: 500;
  letter-spacing: 0.06em;
  color: var(--color-text-primary);
  text-transform: uppercase;
}

.project-year {
  font-family: var(--font-mono);
  font-size: 0.62rem;
  letter-spacing: 0.1em;
  color: var(--color-text-muted);
  flex-shrink: 0;
}

.project-bullets {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
  padding: 0;
}

.project-bullets li {
  font-size: 0.775rem;
  line-height: 1.6;
  color: var(--color-text-secondary);
  font-weight: 400;
  padding-left: 1rem;
  position: relative;
}

.project-bullets li::before {
  content: '—';
  position: absolute;
  left: 0;
  color: var(--color-text-muted);
  font-size: 0.75rem;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-top: 0.15rem;
}
</style>
