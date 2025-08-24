<script>
    let isOpen = false; // for mobile menu toggle
</script>

<navbar class="fixed top-0 w-full bg-[#1a1a1a] shadow-sm z-50">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center py-4">
        
        <!-- Title-->
        <div class="title flex-shrink-0 text-2xl font-bold mr-70">
            YASMINE SUBBAGH
        </div>

        <!-- Desktop Menu -->
        <div class="hidden md:flex md:space-x-6">
            <a href="/" class="nav-link">About</a>
            <a href="/experience" class="nav-link">Experience</a>
            <a href="/projects" class="nav-link">Projects</a>
            <a href="/skills" class="nav-link">Skills</a>
            <a href="/education" class="nav-link">Education</a>
            <a href="/contact" class="nav-link">Contact</a>
            <a href="/yasmine_subbagh_full_resume.pdf" target="_blank" rel="noopener noreferrer" class="nav-link">Resume</a>
        </div>

        <!-- Mobile Menu Button -->
        <button class="md:hidden p-2 rounded-md focus:outline-none focus:ring-2 focus:ring-green-500"
            on:click={() => (isOpen = !isOpen)}>
            {#if isOpen}
            ✖
            {:else}
            ☰
            {/if}
        </button>
        </div>
  </div>

  <!-- Mobile Menu Dropdown -->
    {#if isOpen}
        <div class="md:hidden bg-[#1a1a1a] shadow-lg">
            <a href="/" class="block px-4 py-2 hover:bg-green-50">About</a>
            <a href="/experience" class="block px-4 py-2 hover:bg-green-50">Experience</a>
            <a href="/projects" class="block px-4 py-2 hover:bg-green-50">Projects</a>
            <a href="/skills" class="block px-4 py-2 hover:bg-green-50">Skills</a>
            <a href="/education" class="block px-4 py-2 hover:bg-green-50">Education</a>
            <a href="/contact" class="block px-4 py-2 hover:bg-green-50">Contact</a>
            <a href="/yasmine_subbagh_full_resume.pdf" target="_blank" rel="noopener noreferrer" class="block px-4 py-2 hover:bg-green-50">Resume</a>
        </div>
    {/if}
</navbar>


<style>
/* Navbar styling */
.title {
  color: rgb(115, 134, 120);
}

navbar {
  background-color: #1a1a1a;
  color: #ffffff; 
  display: flex;
}

/* Navbar links */
.nav-link {
  text-decoration: none;
}

.nav-link:hover {
  color: rgb(115, 134, 120);
}
</style>