<script>
  import { onMount } from 'svelte';
  let titles = [
    'Software Engineer',
    'Full Stack Engineer',
    'AI Engineer',
    'Cloud Engineer'
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
    <section id="about" class="flex flex-col-reverse md:flex-row items-center justify-center rounded-2xl shadow-lg p-10 max-w-4xl mx-auto my-20 min-h-[70vh]">
        <div class="flex-1 flex flex-col justify-center items-center md:items-start text-center md:text-left text-white">
            <div class="h-10 mb-4">
                <span class="green-gradient-text text-2xl md:text-3xl font-mono font-semibold">{currentTitle}</span><span class="text-green-400 animate-pulse">|</span>
            </div>
            <p class="mb-6 max-w-2xl text-lg md:text-xl font-light leading-relaxed">
                I’m a software engineer and researcher passionate about building intelligent, user-centered solutions. With a background in full-stack development and applied machine learning, I enjoy exploring how artificial intelligence can be leveraged to solve real-world problems.
            </p>

            <p class="mb-6 max-w-2xl text-lg md:text-xl font-light leading-relaxed">
                My work spans across designing iOS applications for accessibility, developing scalable IoT systems on AWS, and building AI models for computer vision and natural data classification. 
            </p>
            <p class="mb-6 max-w-2xl text-lg md:text-xl font-light leading-relaxed">
                I thrive at the intersection of software engineering and AI: translating complex data into actionable, meaningful applications. Whether it’s deploying cloud-based systems, training neural networks, or prototyping accessible mobile apps, I’m driven by curiosity and a commitment to developing solutions that make an impact.       
            </p>
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
