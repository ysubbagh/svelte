<script lang="ts">
  import Hero from '$lib/components/hero.svelte';
  import About from '$lib/components/about.svelte';
  import Education from '$lib/components/education.svelte';
  import Skills from '$lib/components/skills.svelte';
  import '../app.css';
</script>

<main class="flex flex-col gap-0">
  <section id="about">
    <About />
    <!-- <Hero /> -->
  </section>

  <section id="education">
    <Education /> 
  </section>

  <section id="experience">
    <!-- <Experience /> -->
  </section>

  <section id="projects">
    <!-- <Projects /> -->
  </section>

  <section id="skills">
    <Skills /> 
  </section>

  <section id="contact">
    <!-- <Contact /> -->
  </section>
</main>
