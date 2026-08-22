<template>
  <section class="section experience-section" aria-labelledby="experience-heading">
    <div class="section-content">
      <span class="section-eyebrow">Work & Education</span>
      <h2 id="experience-heading">Experience</h2>

      <div class="section-scroll">
        <ol class="timeline" role="list">
          <li
            v-for="(item, i) in timeline"
            :key="item.title + item.org"
            class="timeline-item"
          >
            <div class="timeline-marker" aria-hidden="true">
              <div class="marker-dot" :class="{ 'marker-dot--edu': item.type === 'edu' }" />
              <div v-if="i < timeline.length - 1" class="marker-line" />
            </div>
            <div class="timeline-body">
              <span class="timeline-period">{{ item.period }}</span>
              <h3 class="timeline-role">{{ item.title }}</h3>
              <span class="timeline-company">{{ item.org }}</span>
              <ul v-if="item.bullets" class="timeline-bullets">
                <li v-for="b in item.bullets" :key="b">{{ b }}</li>
              </ul>
              <div v-if="item.tags" class="timeline-tags">
                <span v-for="tag in item.tags" :key="tag" class="tag">{{ tag }}</span>
              </div>
            </div>
          </li>
        </ol>
      </div>
    </div>
  </section>
</template>

<script setup>
const timeline = [
  {
    type: 'work',
    title: 'Back End Developer',
    org: 'Zaiti · On-site',
    period: 'Jun 2026 – Aug 2026',
    bullets: [
      'Developed and optimized backend services using Go, NestJS, Redis, and MongoDB, focusing on performance, resilience, and event-driven architecture.',
      'Reduced p50 latency of a key home endpoint from ~653 ms to 139 ms through caching, parallelization, and backend optimization.',
      'Built gRPC services, data scraping pipelines, workshop validation workflows, and an in-house VIN/VDS decoder reaching ~92% coverage on the evaluated fleet dataset.',
      'Performed load and resilience testing using Vegeta and Toxiproxy to identify performance bottlenecks and evaluate database and Redis failure behavior.',
    ],
    tags: ['Go', 'NestJS', 'Redis', 'MongoDB', 'gRPC', 'Vegeta', 'Toxiproxy'],
  },
  {
    type: 'work',
    title: 'Leader',
    org: 'Google Developer Group on Campus · Mustaqbal University',
    period: '2025 – 2026',
    bullets: [
      'Organized technical events, workshops, and developer community initiatives focused on Google technologies.',
      'Led student engagement and industry collaboration to strengthen practical skills, networking, and hands-on project experience.',
    ],
    tags: ['Community', 'Leadership', 'Google Technologies'],
  },
  {
    type: 'work',
    title: 'Flutter Programmer',
    org: 'Kharja · Remote',
    period: 'Feb 2024 – Apr 2024',
    bullets: [
      'Developed Flutter application features with dynamic UI, real-time database integration, and end-to-end data flow.',
      'Integrated Firebase services to support real-time synchronization and application workflows.',
    ],
    tags: ['Flutter', 'Dart', 'Firebase'],
  },
  {
    type: 'edu',
    title: 'Bachelor of Software Engineering',
    org: 'Mustaqbal University · Buraidah, KSA',
    period: '2023 – Present',
    bullets: [
      'GPA: 4.85 — Undergraduate, currently enrolled.',
    ],
    tags: ['GPA 4.85', 'Software Engineering'],
  },
]
</script>

<style scoped>
.experience-section {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 var(--section-padding);
}

.timeline {
  list-style: none;
  display: flex;
  flex-direction: column;
  width: 100%;
}

.timeline-item {
  display: flex;
  gap: 1.5rem;
}

.timeline-marker {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-shrink: 0;
  padding-top: 0.3rem;
}

.marker-dot {
  width: 4px;
  height: 4px;
  background: var(--color-text-primary);
  flex-shrink: 0;
}

.marker-dot--edu {
  background: var(--color-text-muted);
  outline: 1px solid var(--color-text-muted);
  outline-offset: 2px;
}

.marker-line {
  flex: 1;
  width: 1px;
  background: var(--color-border);
  margin-top: 0.5rem;
  min-height: 2rem;
}

.timeline-body {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
  padding-bottom: 2.25rem;
  flex: 1;
}

.timeline-period {
  font-family: var(--font-mono);
  font-size: 0.6rem;
  letter-spacing: 0.1em;
  color: var(--color-text-muted);
}

.timeline-role {
  font-family: var(--font-display);
  font-size: 0.85rem;
  font-weight: 500;
  color: var(--color-text-primary);
  text-transform: uppercase;
  letter-spacing: 0.06em;
  margin-top: 0.1rem;
}

.timeline-company {
  font-family: var(--font-mono);
  font-size: 0.65rem;
  letter-spacing: 0.08em;
  color: var(--color-text-muted);
}

.timeline-bullets {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.35rem;
  margin-top: 0.25rem;
}

.timeline-bullets li {
  font-size: 0.85rem;
  line-height: 1.75;
  color: var(--color-text-secondary);
  font-weight: 400;
  padding-left: 1rem;
  position: relative;
}

.timeline-bullets li::before {
  content: '—';
  position: absolute;
  left: 0;
  color: var(--color-text-muted);
  font-size: 0.75rem;
}

.timeline-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  margin-top: 0.4rem;
}
</style>
