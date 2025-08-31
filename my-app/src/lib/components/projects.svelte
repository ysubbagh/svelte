<script lang="ts">
  export let projects = [
    {
      title: "Portfolio Website",
      description: "A personal portfolio built with SvelteKit and Tailwind CSS, featuring responsive design and dynamic content.",
      tech: ["SvelteKit", "Tailwind CSS", "Vercel", "HTML", "CSS", "JavaScript", "TypeScript"],
      details: "Developed a modern, responsive personal portfolio website using SvelteKit and Tailwind CSS. The site features dynamic content sections for projects, skills, education, and experience, with accessible modal dialogs and interactive UI components. Integrated custom branding, optimized for performance and accessibility, and deployed to Vercel for fast, reliable delivery.",
      github: "https://github.com/ysubbagh/svelte",
      demo: "https://yasminesubbagh.com"
    },
    {
      title: "AI Fungi Identifier",
      description: "Enchancing Mushroom Safety through Backprogated Multi-Layer Perceptron Neural Network Identification",
      tech: ["Python", "Scikit-learn", "NumPy", "Seaborn", "Matplotlib", "Pandas"],
      details: [
        "Developed a classifier for wild mushroom edibility with 99.98% accuracy using a backpropagated multi -layer perceptron implemented from scratch in NumPy, trained on 69,000+ samples.",
        "Engineered features from two datasets and applied principal component analysis (PCA) and random forest feature importance rankings to validate data separability and ensure high-quality model input.",
        "Implemented a full ML pipeline in Python, including data preprocessing, analysis, training, and evaluation, focused on preventing overfitting and ensuring model reliability."
      ],
      github: "https://github.com/ysubbagh/581-final/blob/main/notebook.ipynb",
      paper: "/docs/fatal_fungi.pdf"
    },
    {
      title: "IoT Water Monitor",
      description: "Remote monitoring system for residential rainwater harvesting tanks, aimed at improving water management for home gardeners.",
      tech: ["AWS", "Python", "Flask", "Arduino", "EC2", "DynamoDB", "IoT Core", "Lambda","API Gateway"],
      details: [
        "Designed and built an end-to-end IoT system to solve a real personal problem: tracking rainwater levels in outdoor storage tanks to reduce household utility costs.",
        "Built a scalable AWS pipeline: IoT Core for message ingestion, DynamoDB for storage, and Lambda/API Gateway to expose RESTful endpoints.",
        "Developed a responsive Flask web app hosted on EC2 for real-time data visualization and user management, with automated threshold-based alerts via email."
      ],
      github: "https://github.com/ysubbagh/532-final",
      paper: "/docs/smart_yard.pdf"
    },
    {
      title: "AI Vehicle Detection",
      description: "A comparative study of deep learning models for vehicle detection and segmentation, analyzing trade-offs between accuracy and inference speed.",
      tech: ["Python", "TensorFlow", "Dectron2"],
      details: [
        "Fine-tuned a Mask RCNN with Stanford Cars and COCO subset dataset to detect and segment vehicles in traffic scenes.",
        "Evaluated performance, inference speed, and application suitability by comparing the 2-stage model to a 1-stage models and a hybrid ensemble (Faster R-CNN + YOLOv5), analyzing mAP and resource trade-offs across scenarios such as real-time inference vs. high-precision annotation."
      ],
      paper: "/docs/object_detection.pdf"
    },
    {
      title: "Inverse Assembler",
      description: "A command-line disassembler built from scratch in 68K Assembly to translate machine code into human-readable instructions.",
      tech: ["ARM Assembly", "68K Assembly", "EASy68K"],
      details: [
        "Built a command-line assembly disassembler in Motorola 680000 Assembly translating binary machine code into human-readable assembly instructions with support for advanced opcode parsing."
      ],
      github: "https://github.com/ysubbagh/68Kdissasembler",
    },
    {
      title: "Image Deep Learning",
      description: "A Convolutional Neural Network in MATLAB for ASL letter classification, achieving 2nd place in a Kaggle competition.",
      tech: ["MATLAB"],
      details: [
        "Designed, implemented, and trained a convolutional neural network in MATLAB to correctly classify American Sign Language (ASL) MNIST image data.",
        "Improved model accuracy by 61% through data preprocessing and hyperparameter tuning, earning 2nd place in a Kaggle competition.",
      ],
      github: "https://github.com/TheGortDragon/css-485-group-7-final-project",
    }
  ];

  interface Project {
    title: string;
    description: string;
    tech: string[];
    details: string | string[];
    github?: string;
    demo?: string;
    paper?: string;
  }

  let showModal = false;
  let modalProject: Project | null = null;

  function openModal(project: Project) {
    modalProject = project;
    showModal = true;
  }
  function closeModal() {
    showModal = false;
    modalProject = null;
  }

  function handleBackdropKeydown(e: KeyboardEvent) {
    if (e.key === 'Enter' || e.key === ' ') {
      closeModal();
    }
  }

  function handleKeydown(e: KeyboardEvent) {
    if (showModal && e.key === 'Escape') {
      closeModal();
    }
  }
</script>

<svelte:window on:keydown={handleKeydown} />

<section class="w-full max-w-5xl mx-auto my-16 px-2 font-[Inter,sans-serif]">
  <h2 class="text-2xl md:text-3xl font-semibold mb-8 text-white text-center">Projects</h2>
  <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
    {#each projects as project}
      <div class="bg-white/5 rounded-xl shadow-lg p-6 flex flex-col justify-between min-h-[260px] border border-white/10 hover:border-[rgb(115,134,120)] transition relative">
        <!-- Details button -->
        <button class="absolute top-4 right-4 bg-[rgb(115,134,120)] text-white text-xs px-3 py-1 rounded-full shadow hover:bg-white hover:text-[rgb(115,134,120)] border border-[rgb(115,134,120)] transition font-semibold" on:click={() => openModal(project)}>Details</button>
        <div>
          <h3 class="text-xl font-bold mb-2 text-white">{project.title}</h3>
          <p class="text-gray-200 mb-4 text-sm font-[Inter,sans-serif]">{project.description}</p>
          <div class="flex flex-wrap gap-2 mb-4">
            {#each project.tech as tech}
              <span class="bg-[rgba(115,134,120,0.6)] text-[rgb(115,134,120)] text-xs px-2 py-1 rounded font-mono">{tech}</span>
            {/each}
          </div>
        </div>
        <div class="flex gap-4 mt-2">
          {#if project.github}
            <a href={project.github} target="_blank" rel="noopener" class="flex items-center gap-2 bg-[rgb(115,134,120)] hover:bg-white hover:text-[rgb(115,134,120)] text-white px-3 py-1 rounded-full text-sm font-semibold border border-[rgb(115,134,120)] transition">
              <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.387.6.113.82-.262.82-.582 0-.288-.01-1.05-.015-2.06-3.338.725-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.09-.745.082-.73.082-.73 1.205.085 1.84 1.237 1.84 1.237 1.07 1.835 2.807 1.305 3.492.998.108-.776.42-1.305.763-1.605-2.665-.3-5.466-1.335-5.466-5.93 0-1.31.468-2.38 1.236-3.22-.124-.303-.536-1.523.117-3.176 0 0 1.008-.322 3.3 1.23a11.5 11.5 0 0 1 3-.405c1.02.004 2.045.138 3 .405 2.288-1.552 3.294-1.23 3.294-1.23.655 1.653.243 2.873.12 3.176.77.84 1.234 1.91 1.234 3.22 0 4.61-2.805 5.625-5.475 5.922.432.372.816 1.104.816 2.222 0 1.604-.015 2.896-.015 3.29 0 .322.216.697.825.578C20.565 21.796 24 17.3 24 12c0-6.63-5.37-12-12-12z"/></svg>
              GitHub
            </a>
          {/if}
          {#if project.demo}
            <a href={project.demo} target="_blank" rel="noopener" class="flex items-center gap-2 bg-[rgb(115,134,120)] hover:bg-white hover:text-[rgb(115,134,120)] text-white px-3 py-1 rounded-full text-sm font-semibold border border-[rgb(115,134,120)] transition">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M18 13v6a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6m5-3h3m0 0v3m0-3-9 9"/></svg>
              Live Demo
            </a>
          {/if}
          {#if project.paper}
            <a href={project.paper} target="_blank" rel="noopener" class="flex items-center gap-2 bg-[rgb(115,134,120)] hover:bg-white hover:text-[rgb(115,134,120)] text-white px-3 py-1 rounded-full text-sm font-semibold border border-[rgb(115,134,120)] transition">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/></svg>
              Paper
            </a>
          {/if}
        </div>
      </div>
    {/each}

    {#if showModal && modalProject}
      <div class="modal-backdrop fixed inset-0 z-50 flex items-center justify-center bg-black/60 backdrop-blur-sm focus:outline-none" role="dialog" aria-modal="true" aria-label="Project details dialog. Press Escape to close." tabindex="0" on:click={closeModal} on:keydown={handleBackdropKeydown}>
        <div class="modal-content bg-[#232323] rounded-xl shadow-2xl p-8 max-w-lg w-full relative animate-fadein" role="document" on:click|stopPropagation>
          <button class="absolute top-4 right-4 text-white bg-[rgb(115,134,120)] hover:bg-white hover:text-[rgb(115,134,120)] rounded-full px-3 py-1 text-xs font-semibold border border-[rgb(115,134,120)] transition" on:click={closeModal} aria-label="Close project details dialog">Close</button>
          <h3 class="text-2xl font-bold mb-2 text-white">{modalProject.title}</h3>
          <p class="text-gray-200 mb-4 text-base">{modalProject.description}</p>
            {#if Array.isArray(modalProject.details)}
              <ul class="text-gray-200 mb-4 text-base list-disc list-inside">
                {#each modalProject.details as detail}
                  <li>{detail}</li>
                {/each}
              </ul>
            {:else if modalProject.details}
              <p class="text-gray-200 mb-4 text-base">{modalProject.details}</p>
            {:else}
              <p class="text-gray-200 mb-4 text-base">{modalProject.description}</p>
            {/if}
          <div class="flex flex-wrap gap-2 mb-4">
            {#each modalProject.tech as tech}
              <span class="bg-[rgba(115,134,120,0.6)] text-[rgb(115,134,120)] text-xs px-2 py-1 rounded font-mono">{tech}</span>
            {/each}
          </div>
          <div class="flex gap-4 mt-2">
            {#if modalProject.github}
              <a href={modalProject.github} target="_blank" rel="noopener" class="flex items-center gap-2 bg-[rgb(115,134,120)] hover:bg-white hover:text-[rgb(115,134,120)] text-white px-3 py-1 rounded-full text-sm font-semibold border border-[rgb(115,134,120)] transition">
                <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.387.6.113.82-.262.82-.582 0-.288-.01-1.05-.015-2.06-3.338.725-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.09-.745.082-.73.082-.73 1.205.085 1.84 1.237 1.84 1.237 1.07 1.835 2.807 1.305 3.492.998.108-.776.42-1.305.763-1.605-2.665-.3-5.466-1.335-5.466-5.93 0-1.31.468-2.38 1.236-3.22-.124-.303-.536-1.523.117-3.176 0 0 1.008-.322 3.3 1.23a11.5 11.5 0 0 1 3-.405c1.02.004 2.045.138 3 .405 2.288-1.552 3.294-1.23 3.294-1.23.655 1.653.243 2.873.12 3.176.77.84 1.234 1.91 1.234 3.22 0 4.61-2.805 5.625-5.475 5.922.432.372.816 1.104.816 2.222 0 1.604-.015 2.896-.015 3.29 0 .322.216.697.825.578C20.565 21.796 24 17.3 24 12c0-6.63-5.37-12-12-12z"/></svg>
                GitHub
              </a>
            {/if}
            {#if modalProject.demo}
              <a href={modalProject.demo} target="_blank" rel="noopener" class="flex items-center gap-2 bg-[rgb(115,134,120)] hover:bg-white hover:text-[rgb(115,134,120)] text-white px-3 py-1 rounded-full text-sm font-semibold border border-[rgb(115,134,120)] transition">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M18 13v6a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6m5-3h3m0 0v3m0-3-9 9"/></svg>
                Live Demo
              </a>
            {/if}
            {#if modalProject.paper}
              <a href={modalProject.paper} target="_blank" rel="noopener" class="flex items-center gap-2 bg-[rgb(115,134,120)] hover:bg-white hover:text-[rgb(115,134,120)] text-white px-3 py-1 rounded-full text-sm font-semibold border border-[rgb(115,134,120)] transition">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/></svg>
                Paper
              </a>
            {/if}
          </div>
        </div>
      </div>
    {/if}
  </div>
</section>

<style>
  @keyframes fadein {
    from { opacity: 0; transform: scale(0.98); }
    to { opacity: 1; transform: scale(1); }
  }
  .animate-fadein {
    animation: fadein 0.2s ease;
  }
</style>