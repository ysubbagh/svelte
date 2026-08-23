<script>
    export let experiences = [
        {
            company: "Stoke Space",
            logo: "/logos/stoke.png",
            website: "https://www.stokespace.com/",
            title: "Software Engineer",
            location: "Kent, WA",
            period: "February 2026 – Present",
            description: [
                "Led a year-long cutover of inventory auditing onto a single activity feed: closed logging gaps from 76% to 100%, backfilled ~1.75 million historical records with an idempotent dedupe Temporal pipeline, shipped who/when/where/what filters across 10+ surfaces, and removed dual writes from the hot path.",
                "Built an evaluation harness for Claude-based matching of historical inventory events to existing activity rows, iterating prompts against labeled cases until match quality held while cutting token use by 37%.",
                "Owned automatic percent complete for hardware build tasks. Cut Temporal fanout from O(N) to O(1) per work item after instrumenting the bottleneck in Datadog.",
                "Sole engineer for customer-defined inventory flags. Users create custom issue tags and automation rules instead of single hardcoded defect tags, then see those tags on inventory in the build tracker.",
                "Led 0-1 for manufacturing task scheduling. Turned a vague schedule ask into one model with a DAG and a Gantt, evaluated OSS graph and Gantt libraries vs building in-house, and built the end-to-end implementation.",
                "Spearheaded and owned the development, deployment, and operation of a coffee chat bot that automatically pairs employees for weekly 1:1s. Scaled adoption to a company-wide 500+ users, plus additional sub-teams concurrently."
            ]
        },
        {
            company: "Stoke Space",
            logo: "/logos/stoke.png",
            website: "https://www.stokespace.com/",
            title: "Software Engineer Intern",
            location: "Kent, WA",
            period: "September 2025 – February 2026",
            description: [
            ]
        },
        {
            company: "UWB IDEA Lab",
            logo: "/logos/idea.png",
            website: null,
            title: "Research Assistant (Lead Full Stack iOS Engineer)",
            location: "Bothell, WA",
            period: "March 2024 – January 2025",
            description: [
                "Directed the end-to-end design and prototyping of an iOS communication app in Swift for children with speech impediments.",
                "Conducted user requirement gathering with PMs and Speech Pathologists to design the back-end SQLite database to support personalized communication workflows for various use-cases."
            ]
        },
        {
            company: "OneRadio Corp.",
            logo: "/logos/oneradio.png",
            website: "http://www.oneradiocorp.com",
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
            company: "OneRadio Corp.",
            logo: "/logos/oneradio.png",
            website: "http://www.oneradiocorp.com",
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

<section class="w-full max-w-5xl mx-auto my-16 px-2 font-[Inter,sans-serif]">
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
                                    <div class="company-name-location">
                                        {#if exp.website}
                                            <a href={exp.website} target="_blank" rel="noopener noreferrer" class="company-name">
                                                {exp.company}
                                            </a>
                                        {:else}
                                            <span class="company-name no-link">{exp.company}</span>
                                        {/if}
                                        <span class="location">{exp.location}</span>
                                    </div>
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
    /* Gradient border */
    .timeline {
        position: relative;
        margin-left: 1.5rem;
        border-left: 6px solid transparent;
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
        font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
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
        display: inline;
        text-decoration: none;
        transition: color 0.3s ease;
    }
    .company-name:hover {
        color: #a3c1a8;
        text-decoration: underline;
    }
    .company-name.no-link:hover {
        color: inherit;
        text-decoration: none;
    }
    .location {
        font-size: 0.95rem;
        color: #aaa;
        margin-left: 0.5rem;
        display: inline;
    }
    .company-name-location {
        display: flex;
        flex-direction: row;
        align-items: center;
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
        .company-name-location {
            flex-direction: column;
            align-items: flex-start;
        }
        .location {
            margin-left: 0;
            margin-top: 0.1rem;
            display: block;
        }
        .period-right {
            margin-left: 0;
            text-align: left;
            min-width: unset;
        }
    }
</style>
