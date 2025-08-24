<script>
    let isOpen = false; // for mobile menu toggle
</script>

<nav class="fixed top-0 w-full bg-[rgba(10,10,10,0.95)] backdrop-blur-md shadow-sm z-50">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
        
        <!-- Title-->
        <div class="flex-shrink-0 text-2xl font-bold text-green-400 mr-8">
            YASMINE SUBBAGH
        </div>

        <!-- Desktop Menu -->
        <div class="hidden md:flex md:space-x-6">
            <a href="/" class="hover:text-green-700">About</a>
            <a href="/experience" class="hover:text-green-700">Experience</a>
            <a href="/projects" class="hover:text-green-700">Projects</a>
            <a href="/skills" class="hover:text-green-700">Skills</a>
            <a href="/education" class="hover:text-green-700">Education</a>
            <a href="/contact" class="hover:text-green-700">Contact</a>
            <a href="/resume" class="hover:text-green-700">Resume</a>
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
        <div class="md:hidden bg-[rgba(10,10,10,0.95)] shadow-lg">
            <a href="/" class="block px-4 py-2 hover:bg-green-50">About</a>
            <a href="/experience" class="block px-4 py-2 hover:bg-green-50">Experience</a>
            <a href="/projects" class="block px-4 py-2 hover:bg-green-50">Projects</a>
            <a href="/skills" class="block px-4 py-2 hover:bg-green-50">Skills</a>
            <a href="/education" class="block px-4 py-2 hover:bg-green-50">Education</a>
            <a href="/contact" class="block px-4 py-2 hover:bg-green-50">Contact</a>
            <a href="/resume" class="block px-4 py-2 hover:bg-green-50">Resume</a>
        </div>
    {/if}
</nav>



<style>
/* Navbar styling with opacity */
nav {
  background-color:rgba(10, 10, 10, 0.95); /* dark grey with 90% opacity */
  color: #ffffff; /* readable text */
  display: flex;
  backdrop-filter: blur(5px); /* subtle blur behind the navbar */
}

/* Navbar links */
nav a {
  text-decoration: none;
}

nav a:hover {
  text-decoration: underline;
}
</style>