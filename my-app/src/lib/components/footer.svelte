<script lang="ts"> 
    const year: number = new Date().getFullYear();
</script>

<footer class="bg-green-900 text-gray-100 py-10 mt-12">
    <div class="max-w-6xl mx-auto px-6 grid grid-cols-[2fr_.3fr_1fr] gap-8">

    <!-- Left: Title + Body -->
    <div>
        <h2 class="text-xl font-bold mb-2">Yasmine Subbagh</h2>
        <p class="text-sm text-gray-300">
            Software Engineer 
        </p>
        <p class="text-sm text-gray-300">
            I love building digital experiences and learning new things.  
        </p>
        <p class="mt-4 text-xs text-gray-400">© {year} All rights reserved.</p>
    </div>

    <!-- Middle: Nav Links -->
    <div class="flex flex-col space-y-2 pl-8">
        <h2 class="text-xl font-bold mb-2">Links</h2>
        <a href="/" class="hover:text-amber-300">About</a>
        <a href="/experience" class="hover:text-amber-300">Experience</a>
        <a href="/projects" class="hover:text-amber-300">Projects</a>
        <a href="/skills" class="hover:text-amber-300">Skills</a>
    </div>

    <!-- Right: Contact Links -->
    <div class="flex flex-col space-y-2 md:items-end">
        <h2 class="text-xl font-bold mb-2">Connect</h2>
        <!-- GitHub -->
        <a href="https://github.com/ysubbagh" target="_blank" rel="noopener noreferrer">
            <svg class="w-6 h-6 fill-current text-white hover:text-green-400" viewBox="0 0 24 24">
            <path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.387.6.113.82-.262.82-.582 0-.288-.01-1.05-.015-2.06-3.338.725-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.09-.745.082-.73.082-.73 1.205.085 1.84 1.237 1.84 1.237 1.07 1.835 2.807 1.305 3.492.998.108-.776.42-1.305.763-1.605-2.665-.3-5.466-1.335-5.466-5.93 0-1.31.468-2.38 1.236-3.22-.124-.303-.536-1.523.117-3.176 0 0 1.008-.322 3.3 1.23a11.5 11.5 0 0 1 3-.405c1.02.004 2.045.138 3 .405 2.288-1.552 3.294-1.23 3.294-1.23.655 1.653.243 2.873.12 3.176.77.84 1.234 1.91 1.234 3.22 0 4.61-2.805 5.625-5.475 5.922.432.372.816 1.104.816 2.222 0 1.604-.015 2.896-.015 3.29 0 .322.216.697.825.578C20.565 21.796 24 17.3 24 12c0-6.63-5.37-12-12-12z"/>
            </svg>
        </a>

        <!-- LinkedIn -->
        <a href="https://www.linkedin.com/in/yasmine-subbagh/" target="_blank" rel="noopener noreferrer">
            <svg class="w-6 h-6 fill-current text-white hover:text-green-400" viewBox="0 0 24 24">
            <path d="M4.98 3.5C3.34 3.5 2 4.85 2 6.49c0 1.64 1.34 2.99 2.98 2.99s2.98-1.35 2.98-2.99c0-1.64-1.34-2.99-2.98-2.99zM2.4 21.5h5.16v-11.44H2.4V21.5zM9.54 10.06h4.95v1.55h.07c.69-1.31 2.37-2.7 4.87-2.7 5.21 0 6.17 3.42 6.17 7.86V21.5h-5.16v-6.96c0-1.66-.03-3.79-2.31-3.79-2.31 0-2.66 1.8-2.66 3.66v7.09h-5.15V10.06z"/>
            </svg>
        </a>

        <!-- Email -->
        <a href="mailto:ysubbagh@gmail.com" target="_blank" rel="noopener noreferrer">
            <svg class="w-6 h-6 fill-current text-white hover:text-green-400" viewBox="0 0 24 24">
            <path d="M12 12.713l11.985-8.713H0L12 12.713zM12 14.887l-12-8.713v13.826h24V6.174l-12 8.713z"/>
            </svg>
        </a>

    </div>
</footer>
