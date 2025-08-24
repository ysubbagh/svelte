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
        <h2 class="text-xl font-bold mb-2">Contact</h2>
        <a href="https://github.com/yourusername" target="_blank" rel="noopener"
            class="hover:text-amber-300">GitHub</a>
        <a href="https://linkedin.com/in/yourusername" target="_blank" rel="noopener"
            class="hover:text-amber-300">LinkedIn</a>
        <a href="mailto:youremail@example.com" class="hover:text-amber-300">Email</a>
    </div>

    </div>
</footer>
