<script>
  import { onMount } from 'svelte';
  let titles = [
    'Software Engineer',
    'Full Stack Engineer',
    'AI Engineer'
  ];
  let currentTitle = '';
  let titleIndex = 0;
  let charIndex = 0;
  let typing = true;

  function typeTitle() {
    if (typing) {
      if (charIndex < titles[titleIndex].length) {
        currentTitle += titles[titleIndex][charIndex];
        charIndex++;
        setTimeout(typeTitle, 80);
      } else {
        typing = false;
        setTimeout(typeTitle, 1200);
      }
    } else {
      if (charIndex > 0) {
        currentTitle = currentTitle.slice(0, -1);
        charIndex--;
        setTimeout(typeTitle, 40);
      } else {
        typing = true;
        titleIndex = (titleIndex + 1) % titles.length;
        setTimeout(typeTitle, 300);
      }
    }
  }

  onMount(() => {
    typeTitle();
  });
</script>

<div class="relative w-full">
  <section id="about" class="flex flex-col-reverse md:flex-row items-center md:items-center justify-center rounded-2xl shadow-lg p-4 md:p-10 w-full md:max-w-6xl mx-auto my-20 min-h-[70vh]">
    <div class="flex-1 flex flex-col justify-center items-start text-left">
      <div class="h-10 mb-8 w-full flex items-center">
        <span class="green-gradient-text text-lg md:text-3xl font-light">{currentTitle}</span><span class="text-green-400 animate-pulse ml-1">|</span>
      </div>
      <p class="mb-6 max-w-2xl text-sm md:text-xl font-extralight leading-relaxed text-gray-300">
        I’m a software engineer and researcher passionate about building intelligent, user-centered solutions. With a background in full-stack development and applied machine learning, I enjoy exploring how artificial intelligence can be leveraged to solve real-world problems.
      </p>

      <p class="mb-6 max-w-2xl text-sm md:text-xl font-extralight leading-relaxed text-gray-300">
        My work spans across designing iOS applications for accessibility, developing scalable IoT systems on AWS, and building AI models for computer vision and natural data classification. 
      </p>
      <p class="mb-6 max-w-2xl text-sm md:text-xl font-extralight leading-relaxed text-gray-300">
        I thrive at the intersection of software engineering and AI: translating complex data into actionable, meaningful applications. Whether it’s deploying cloud-based systems, training neural networks, or prototyping accessible mobile apps, I’m driven by curiosity and a commitment to developing solutions that make an impact.       
      </p>
    </div>
  <div class="hidden md:flex flex-col items-center justify-center mb-8 md:mb-0 md:ml-10">
            <img src="/me.jpg" alt="Yasmine Subbagh" class="w-48 h-48 md:w-64 md:h-64 object-cover rounded-xl border-4 border-[rgb(115,134,120)] shadow-lg mb-4 bg-[#232323]" loading="lazy" />
      <div class="flex gap-4 mt-2">
        <a href="mailto:ysubbagh@gmail.com" target="_blank" rel="noopener" aria-label="Email" class="text-[rgb(115,134,120)] hover:text-white bg-white/10 hover:bg-[rgb(115,134,120)] rounded-full p-2 transition border border-[rgb(115,134,120)]">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M16 12l-4 4-4-4m8-4H4a2 2 0 0 0-2 2v8a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2v-8a2 2 0 0 0-2-2z"/></svg>
        </a>
        <a href="https://www.linkedin.com/in/yasmine-subbagh/" target="_blank" rel="noopener" aria-label="LinkedIn" class="text-[rgb(115,134,120)] hover:text-white bg-white/10 hover:bg-[rgb(115,134,120)] rounded-full p-2 transition border border-[rgb(115,134,120)]">
          <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.76 0-5 2.24-5 5v14c0 2.76 2.24 5 5 5h14c2.76 0 5-2.24 5-5v-14c0-2.76-2.24-5-5-5zm-11 19h-3v-9h3v9zm-1.5-10.28c-.97 0-1.75-.79-1.75-1.75s.78-1.75 1.75-1.75 1.75.79 1.75 1.75-.78 1.75-1.75 1.75zm15.5 10.28h-3v-4.5c0-1.08-.02-2.47-1.5-2.47-1.5 0-1.73 1.17-1.73 2.39v4.58h-3v-9h2.89v1.23h.04c.4-.75 1.38-1.54 2.84-1.54 3.04 0 3.6 2 3.6 4.59v4.72z"/></svg>
        </a>
        <a href="https://github.com/ysubbagh" target="_blank" rel="noopener" aria-label="GitHub" class="text-[rgb(115,134,120)] hover:text-white bg-white/10 hover:bg-[rgb(115,134,120)] rounded-full p-2 transition border border-[rgb(115,134,120)]">
          <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.387.6.113.82-.262.82-.582 0-.288-.01-1.05-.015-2.06-3.338.725-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.09-.745.082-.73.082-.73 1.205.085 1.84 1.237 1.84 1.237 1.07 1.835 2.807 1.305 3.492.998.108-.776.42-1.305.763-1.605-2.665-.3-5.466-1.335-5.466-5.93 0-1.31.468-2.38 1.236-3.22-.124-.303-.536-1.523.117-3.176 0 0 1.008-.322 3.3 1.23a11.5 11.5 0 0 1 3-.405c1.02.004 2.045.138 3 .405 2.288-1.552 3.294-1.23 3.294-1.23.655 1.653.243 2.873.12 3.176.77.84 1.234 1.91 1.234 3.22 0 4.61-2.805 5.625-5.475 5.922.432.372.816 1.104.816 2.222 0 1.604-.015 2.896-.015 3.29 0 .322.216.697.825.578C20.565 21.796 24 17.3 24 12c0-6.63-5.37-12-12-12z"/></svg>
        </a>
      </div>
    </div>
  </section>
</div>

<style>
.green-gradient-text {
  background: linear-gradient(90deg, #a8e063, #38ef7d, #43cea2, #185a9d, #5bffb0, #6ee7b7, #22c55e, #16a34a, #a8e063);
  background-size: 200% auto;
  color: transparent;
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: green-move 3s linear infinite;
}
@keyframes green-move {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}
</style>