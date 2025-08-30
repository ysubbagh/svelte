<script>
  export let experiences = [
    {
      company: "UWB IDEA Lab",
      logo: "/logos/idea.png", 
      title: "Full Stack iOS Engineer / Research Assistant",
      location: "Bothell, WA",
      period: "March 2024 – Present",
      description: [
        "Led the end-to-end design and prototyping of an iOS communication app in Swift for non-verbal children that require speech assistance.",
        "Lead user requirement gathering with PMs and Speech Pathologists to design the back-end SQLite database to support personalized communication workflows for various use-cases."
      ]
    },
    {
      company: "OneRadio Corp",
      logo: "/logos/oneradio.png", 
      title: "Software Engineer Intern",
      location: "Seattle, WA",
      period: "June 2024 – September 2024",
      description: [
        "Led the research and evaluation process to select a secure remote development solution for collaborative code access. Established criteria around security, speed, cost, and accessibility.",
        "Led the migration of 3 primary codebases to secure, cloud-based version control on AWS, improving development workflow for 5 engineers working with the codebase.",
        "Designed and implemented an LSTM based AI model to predict radio wave behavior."
      ]
    },
    {
      company: "OneRadio Corp",
      logo: "/logos/oneradio.png",
      title: "Software Engineer Intern",
      location: "Seattle, WA",
      period: "June 2023 – September 2023",
      description: [
        "Performed and documented black box testing to validate system functionality and support reliable software delivery.",
        "Debugged and maintained critical legacy code in C, contributing to stability and performance improvements."
      ]
    }
  ];
</script>

<section class="w-full max-w-5xl mx-auto my-16 px-2">
    <h2 class="text-2xl md:text-3xl font-semibold mb-8 text-white text-center">Work Experience</h2>
    <div class="timeline">
        {#each experiences as exp, i}
        <div class="timeline-entry">
            <div class="timeline-dot"></div>
            <div class="timeline-content">
                <div class="flex items-center mb-2">
                    {#if exp.logo}
                    <img src={exp.logo} alt={exp.company + ' logo'} class="company-logo" />
                    {/if}
                    <div class="w-full">
                        <div class="job-title">{exp.title}</div>
                        <div class="flex flex-row flex-wrap items-center justify-between w-full">
                            <div class="company-name">{exp.company} <span class="location">{exp.location}</span></div>
                            <div class="period period-right">{exp.period}</div>
                        </div>
                    </div>
                </div>
                <ul class="description-list">
                    {#each exp.description as bullet}
                    <li>{bullet}</li>
                    {/each}
                </ul>
            </div>
        </div>
        {/each}
    </div>
</section>

<style>
    .timeline {
        position: relative;
        margin-left: 1.5rem;
        border-left: 6px solid transparent;
        /* Gradient border */
    }
    .timeline::before {
        content: "";
        position: absolute;
        left: -6px;
        top: 0;
        width: 6px;
        height: 100%;
        border-radius: 3px;
        background: linear-gradient(to bottom, #73a87a, #738676, #738676, #232323);
        z-index: 0;
    }
    .timeline-entry {
        position: relative;
        margin-bottom: 2.5rem;
        padding-left: 1.5rem;
    }
    .timeline-dot {
        position: absolute;
        left: -1.1rem;
        top: 0.7rem;
        width: 1rem;
        height: 1rem;
        background: rgb(115,134,120);
        border-radius: 50%;
        border: 2px solid #fff;
        z-index: 1;
    }
    .timeline-content {
        background: rgba(255,255,255,0.03);
        border-radius: 0.5rem;
        padding: 1.25rem 1.5rem;
        box-shadow: 0 1px 4px 0 rgba(0,0,0,0.08);
    }
    .company-logo {
      width: 3.5rem;
      height: 3.5rem;
      object-fit: contain;
      margin-right: 1.25rem;
      border-radius: 0.5rem;
      background: #fff;
      box-shadow: 0 1px 4px 0 rgba(0,0,0,0.08);
    }
    .job-title {
        font-size: 1.1rem;
        font-weight: 600;
        color: #fff;
    }
    .company-name {
        font-size: 1rem;
        color: rgb(115,134,120);
        font-weight: 500;
    }
    .location {
        font-size: 0.95rem;
        color: #aaa;
        margin-left: 0.5rem;
    }
  .period {
    font-size: 0.95rem;
    color: #bbb;
    margin-bottom: 0.5rem;
  }
  .period-right {
    margin-left: auto;
    text-align: right;
    min-width: 120px;
  }
    .description-list {
        margin: 0.5rem 0 0 0;
        padding-left: 1.2rem;
        color: #eee;
        font-size: 1rem;
        list-style: disc;
    }
  @media (max-width: 640px) {
    .timeline-content {
      padding: 1rem;
    }
    .company-logo {
      width: 2rem;
      height: 2rem;
      margin-right: 0.5rem;
    }
    .flex.flex-row.flex-wrap.items-center.justify-between.w-full {
      flex-direction: column;
      align-items: flex-start;
    }
    .period-right {
      margin-left: 0;
      text-align: left;
      min-width: unset;
    }
  }
</style>