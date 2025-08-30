<script>
  export let education = [
    {
      degree: 'M.S. Computer Science and Software Engineering',
      institution: 'University of Washington',
      location: 'Bothell, WA',
      duration: '2024 – Present',
      gpa: 3.74,
      description: 'Relevant coursework: Machine Learning, Deep Learning, Internet of Things (IoT), Software Management.'
    },
    {
      degree: 'B.S. Computer Science and Software Engineering',
      institution: 'University of Washington',
      location: 'Bothell, WA',
      duration: '2020 – 2024',
      gpa: 3.67,
      description: 'Relevant coursework: Data Structures & Algorithms, Database Systems, Operating Systems, Cloud Computing, Artifical Neural Networks, Hardware and Computer Organization, Web Media, Usability Engineering.'
      }
  ];
</script>

<section id="education" class="w-full max-w-5xl mx-auto my-16 px-2">
  <h2 class="text-2xl md:text-3xl font-semibold mb-8 text-white text-center">Education</h2>
  <div class="flex flex-col gap-6">
    {#each education as edu}
  <div class="w-full bg-[#232323] rounded-xl shadow-md p-6 border border-gray-800 text-gray-300 mx-auto flex items-center gap-4">
        <img src="/logos/uw.png" alt="UW Logo" class="hidden md:block w-30 h-30 object-contain rounded-lg p-2 shadow-md" />
        <div class="flex-1">
          <div class="flex flex-col md:flex-row md:items-center md:justify-between mb-2">
            <span class="text-lg md:text-xl font-medium text-white">{edu.degree}</span>
            <span class="text-sm md:text-base text-gray-400 mt-1 md:mt-0">{edu.duration}</span>
          </div>
          <div class="flex flex-col md:flex-row md:items-center md:justify-between mb-1">
            <span class="text-base md:text-lg font-light text-gray-400">{edu.institution}</span>
            <span class="text-sm md:text-base text-gray-400 mt-1 md:mt-0">{edu.location}</span>
          </div>
          <div class="text-sm md:text-base text-gray-400 mb-1">GPA: {edu.gpa} / 4.0</div>
          <div class="text-sm md:text-base text-gray-300">{edu.description}</div>
        </div>
      </div>
    {/each}
  </div>
</section>
