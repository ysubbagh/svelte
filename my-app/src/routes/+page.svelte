<script lang="ts">
  import About from '$lib/components/about.svelte';
  import Education from '$lib/components/education.svelte';
  import Skills from '$lib/components/skills.svelte';
  import Experience from '$lib/components/experience.svelte';
  import Projects from '$lib/components/projects.svelte';
  import '../app.css';
</script>

<main class="flex flex-col gap-0">
  <section id="about">
    <About />
  </section>

  <section id="experience">
    <Experience />
  </section>

  <section id="projects">
    <Projects />
  </section>

  <section id="skills">
    <Skills /> 
  </section>

  <section id="education">
    <Education /> 
  </section>
</main>