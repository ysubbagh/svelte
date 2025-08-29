<script>
    const skillLogos = {
        // Languages
        'C': '/skills_logos/langs/c.png',
        'C++': '/skills_logos/langs/cpp.png',
        'Python': '/skills_logos/langs/python.svg',
        'Java': '/skills_logos/langs/java.png',
        'Swift': '/skills_logos/langs/swift.svg',
        'Bash': '/skills_logos/langs/bash.png',
        'ARM Assembly': '/skills_logos/langs/arm.png',
        'Motorola 68000 Assembly': '/skills_logos/langs/68k.png',
        'MATLAB': '/skills_logos/langs/matlab.png',
        // Web
        'JavaScript': '/skills_logos/web/js.png',
        'TypeScript': '/skills_logos/web/ts.svg',
        'HTML': '/skills_logos/web/html.png',
        'CSS': '/skills_logos/web/css.png',
        'RESTful APIs': '/skills_logos/web/rest.svg',
        'Svelte': '/skills_logos/web/svelte.png',
        'Flask': '/skills_logos/web/flask.png',
        'React': '/skills_logos/web/react.png',
        'Next.js': '/skills_logos/web/next.svg',
        'Node.js': '/skills_logos/web/node.svg',
        'Tailwind CSS': '/skills_logos/web/tailwind.png',
        'JSON': '/skills_logos/web/json.png',
        // Cloud, DevOps, DB
        'AWS': '/skills_logos/cloud/aws.png',
        'Azure': '/skills_logos/cloud/azure.png',
        'Docker': '/skills_logos/cloud/docker.png',
        'Git': '/skills_logos/cloud/git.png',
        'MySQL': '/skills_logos/cloud/mysql.png',
        'PostgreSQL': '/skills_logos/cloud/postsql.png',
        // ML/Data
        'TensorFlow': '/skills_logos/ml/tf.png',
        'PyTorch': '/skills_logos/ml/py.png',
        'Keras': '/skills_logos/ml/keras.png',
        'scikit-learn': '/skills_logos/ml/scikit.png',
        'Pandas': '/skills_logos/ml/pandas.png',
        'NumPy': '/skills_logos/ml/numpy.svg',
        'NLTK': '/skills_logos/ml/nltk.png',
        'Seaborn': '/skills_logos/ml/seaborn.svg',
        // Dev Tools
        'Visual Studio Code': '/skills_logos/dev/vsc.png',
        'Figma': '/skills_logos/dev/figma.png',
        'Quatrics': '/skills_logos/dev/qual.png',
        'ArcGIS Pro': '/skills_logos/dev/gis.png',
        'LaTeX': '/skills_logos/dev/latex.png',
    };

    export let skills = [
        {
            category: 'Programming & Scripting Languages',
            items: ['C', 'C++', 'Python', 'Java', 'Swift', 'Bash', 'ARM Assembly', 'Motorola 68000 Assembly', 'MATLAB']
        },
        {
            category: 'Web Development',
            items: ['JavaScript', 'TypeScript', 'HTML', 'CSS', 'RESTful APIs', 'Svelte', 'Flask', 'React', 'Next.js', 'Node.js', 'Tailwind CSS', 'JSON']
        },
        {
            category: 'Cloud, DevOps, & Databases',
            items: ['AWS', 'Azure', 'Docker', 'Git', 'MySQL', 'PostgreSQL']
        },
        {
            category: 'Machine Learning & Data Science',
            items: ['TensorFlow', 'PyTorch', 'Keras', 'scikit-learn', 'Pandas', 'NumPy', 'NLTK', 'Seaborn']
        },
        {
            category: 'Development Tools',
            items: ['Visual Studio Code', 'Figma', 'Quatrics', 'ArcGIS Pro', 'LaTeX']
        }
    ];

    const getLogo = (item) => skillLogos[item];
</script>

<section id="skills" class="w-full max-w-5xl mx-auto my-16 px-2">
    <h2 class="text-2xl md:text-3xl font-semibold mb-10 text-white text-center">Skills</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-10 place-items-center">
        {#each skills as skill, i}
        <div class="w-full max-w-3xl bg-[#232323] border border-gray-700 rounded-2xl shadow-md flex flex-col items-center py-7 px-4 {i === 4 ? 'md:col-span-2 mx-auto' : ''}">
            <span class="text-lg md:text-xl font-semibold text-gray-200 mb-3 tracking-wide">{skill.category}</span>
            <ul class="flex flex-wrap gap-3 justify-center">
            {#each skill.items as item}
                <li class="bg-[rgb(115,134,120)] border border-gray-700 text-white px-5 py-2 rounded-full text-base md:text-lg flex items-center gap-2 shadow-sm">
                {#if getLogo(item)}
                    <img src={getLogo(item)} alt={item + ' logo'} class="w-6 h-6 inline-block" loading="lazy" />
                {/if}
                {item}
                </li>
            {/each}
            </ul>
        </div>
        {/each}
    </div>
</section>
