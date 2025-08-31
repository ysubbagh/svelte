<script>
    const skillLogos = {
        // Languages
        'C': '/logos/langs/c.png',
        'C++': '/logos/langs/cpp.png',
        'Python': '/logos/langs/python.svg',
        'Java': '/logos/langs/java.png',
        'Swift': '/logos/langs/swift.svg',
        'Cuda': '/logos/langs/cuda.svg',
        'Bash': '/logos/langs/bash.png',
        'ARM Assembly': '/logos/langs/arm.png',
        'Motorola 68000 Assembly': '/logos/langs/68k.png',
        'MATLAB': '/logos/langs/matlab.png',
        'Arduino': '/logos/langs/arduino.png',
        // Web
        'JavaScript': '/logos/web/js.png',
        'TypeScript': '/logos/web/ts.svg',
        'HTML': '/logos/web/html.png',
        'CSS': '/logos/web/css.png',
        'RESTful APIs': '/logos/web/rest.svg',
        'Svelte': '/logos/web/svelte.png',
        'Flask': '/logos/web/flask.png',
        'React': '/logos/web/react.png',
        'Next.js': '/logos/web/next.svg',
        'Node.js': '/logos/web/node.svg',
        'Tailwind CSS': '/logos/web/tailwind.png',
        'JSON': '/logos/web/json.png',
        // Cloud, DevOps, DB
        'AWS': '/logos/cloud/aws.png',
        'Azure': '/logos/cloud/azure.png',
        'Docker': '/logos/cloud/docker.png',
        'Git': '/logos/cloud/git.png',
        'MySQL': '/logos/cloud/mysql.png',
        'PostgreSQL': '/logos/cloud/postsql.png',
        'Vercel': '/logos/cloud/vercel.png',
        'DynamoDB': '/logos/cloud/ddb.png',
        'Supabase': 'logos/cloud/supabase.png',
        // ML/Data
        'TensorFlow': '/logos/ml/tf.png',
        'PyTorch': '/logos/ml/py.png',
        'Keras': '/logos/ml/keras.png',
        'scikit-learn': '/logos/ml/scikit.png',
        'Pandas': '/logos/ml/pandas.png',
        'NumPy': '/logos/ml/numpy.svg',
        'NLTK': '/logos/ml/nltk.png',
        'Seaborn': '/logos/ml/seaborn.svg',
        'Matplotlib': '/logos/ml/matplot.png',
        'Google Gemini API': '/logos/ml/gemini.png',
        // Dev Tools
        'Visual Studio Code': '/logos/dev/vsc.png',
        'Figma': '/logos/dev/figma.png',
        'Qualtrics': '/logos/dev/qual.png',
        'ArcGIS Pro': '/logos/dev/gis.png',
        'LaTeX': '/logos/dev/latex.png',
    };

    export let skills = [
        {
            category: 'Programming Languages',
            items: ['C', 'C++', 'Python', 'Java', 'Swift', 'Cuda', 'Bash', 'ARM Assembly', 'Motorola 68000 Assembly', 'MATLAB', 'Arduino']
        },
        {
            category: 'Web Development',
            items: ['JavaScript', 'TypeScript', 'HTML', 'CSS', 'RESTful APIs', 'Svelte', 'Flask', 'React', 'Next.js', 'Node.js', 'Tailwind CSS', 'JSON']
        },
        {
            category: 'Cloud, DevOps, & Databases',
            items: ['AWS', 'Azure', 'Vercel', 'Docker', 'Git', 'MySQL', 'PostgreSQL', 'DynamoDB', 'Supabase']
        },
        {
            category: 'Machine Learning & Data Science',
            items: ['TensorFlow', 'PyTorch', 'Keras', 'scikit-learn', 'Pandas', 'NumPy', 'NLTK', 'Seaborn', 'Matplotlib', 'Google Gemini API']
        },
        {
            category: 'Development Tools',
            items: ['Visual Studio Code', 'Figma', 'Qualtrics', 'ArcGIS Pro', 'LaTeX']
        }
    ];

    const getLogo = (item) => skillLogos[item];
</script>

<section id="skills" class="w-full max-w-5xl mx-auto my-16 px-2 font-[Inter,sans-serif]">
    <h2 class="text-2xl md:text-3xl font-semibold mb-10 text-white text-center">Skills</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-10 place-items-center">
        {#each skills as skill, i}
            <div class="w-full max-w-3xl bg-[#232323] border border-white/10 hover:border-[rgb(115,134,120)] transition rounded-2xl shadow-md flex flex-col items-center py-7 px-4 {i === 4 ? 'md:col-span-2 mx-auto' : ''}">
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