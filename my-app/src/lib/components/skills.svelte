<script>
  const skillLogos = {
    // Languages
    'C': '/skills_logos/langs/c.png',
    'C++': '/skills_logos/langs/c++.svg.png',
    'Python': '/skills_logos/langs/python.svg',
    'Java': '/skills_logos/langs/java.png',
    'Swift': '/skills_logos/langs/swift.svg',
    'Bash': '/skills_logos/langs/bash.png',
    'ARM Assembly': '/skills_logos/langs/arm.png',
    'Motorola 68000 Assembly': '/skills_logos/langs/68k.svg.png',
    'MATLAB': '/skills_logos/langs/matlab.png',
    // Web
    'JavaScript': '/skills_logos/web/js.svg.png',
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
    'Azure': '/skills_logos/cloud/azure.svg.png',
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
</script>

<section id="skills" class="w-full max-w-5xl mx-auto my-16 px-2">
  <h2 class="text-2xl md:text-3xl font-semibold mb-10 text-white text-center">Skills</h2>
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8 place-items-center auto-rows-fr">
    {#each skills as skill}
      <div class="bg-[#232323] rounded-xl shadow-md p-7 border border-gray-700 text-gray-300 flex flex-col items-center w-full max-w-sm">
        <span class="text-lg md:text-xl font-semibold text-white mb-3">{skill.category}</span>
        <ul class="flex flex-wrap gap-3 justify-center">
          {#each skill.items as item}
            <li class="bg-gray-800 text-gray-200 px-4 py-1.5 rounded-full text-sm md:text-base flex items-center gap-2.5">
              {#if skillLogos[item]}
                <img src={skillLogos[item]} alt={item + ' logo'} class="w-6 h-6 inline-block" loading="lazy" />
              {/if}
              {item}
            </li>
          {/each}
        </ul>
      </div>
    {/each}
  </div>
</section>
