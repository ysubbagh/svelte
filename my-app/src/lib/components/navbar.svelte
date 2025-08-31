<script>
    import { onMount, onDestroy } from 'svelte';
    import { browser } from '$app/environment';

    let isOpen = false; // for mobile menu toggle
    let navbarElement; 

    function closeNavbar() {
        isOpen = false;
    }

    function handleKeydown(event) {
        if (event.key === 'Escape') {
            closeNavbar();
        }
    }

    function handleClickOutside(event) {
        if (navbarElement && !navbarElement.contains(event.target)) {
            closeNavbar();
        }
    }

    // Add event listeners when the component is mounted
    onMount(() => {
        if (browser) {
            document.addEventListener('keydown', handleKeydown);
            document.addEventListener('click', handleClickOutside);
        }
    });

    // Remove event listeners when the component is unmounted
    onDestroy(() => {
        if (browser) {
            document.removeEventListener('keydown', handleKeydown);
            document.removeEventListener('click', handleClickOutside);
        }
    });
</script>

<navbar bind:this={navbarElement} class="fixed top-0 w-full bg-[#1a1a1a] shadow-sm z-50">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center py-4">
        
        <!-- Title-->
    <a href="/" class="title flex-shrink-0 text-2xl font-bold mr-10" style="text-decoration: none;">
            YASMINE SUBBAGH
        </a>

        <!-- Desktop Menu -->
        <div class="hidden md:flex md:space-x-6 ml-60">
            <a href="/#about" class="nav-link">About</a>
            <a href="/#experience" class="nav-link">Experience</a>
            <a href="/#projects" class="nav-link">Projects</a>
            <a href="/#skills" class="nav-link">Skills</a>
            <a href="/#education" class="nav-link">Education</a>
            <a href="/contact" class="nav-link">Contact</a>
            <a href="/yasmine_subbagh_full_resume.pdf" target="_blank" rel="noopener noreferrer" class="nav-link">Resume</a>
        </div>

        <!-- Mobile Menu Button -->
    <button class="md:hidden p-2 rounded-md focus:outline-none focus:ring-2 focus:ring-green-500 text-white bg-[rgb(115,134,120)]"
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
        <div class="md:hidden bg-[#1a1a1a] shadow-lg w-auto absolute right-0 mt-2 mr-4">
            <a href="/#about" class="mobile-nav-link" on:click={() => (isOpen = false)}>About</a>
            <a href="/#experience" class="mobile-nav-link" on:click={() => (isOpen = false)}>Experience</a>
            <a href="/#projects" class="mobile-nav-link" on:click={() => (isOpen = false)}>Projects</a>
            <a href="/#skills" class="mobile-nav-link" on:click={() => (isOpen = false)}>Skills</a>
            <a href="/#education" class="mobile-nav-link" on:click={() => (isOpen = false)}>Education</a>
            <a href="/contact" class="mobile-nav-link" on:click={() => (isOpen = false)}>Contact</a>
            <a href="/docs/yasmine_subbagh_full_resume.pdf" target="_blank" rel="noopener noreferrer" class="mobile-nav-link" on:click={() => (isOpen = false)}>Resume</a>
        </div>
    {/if}
</navbar>


<style>
    /* Navbar styling */
    .title {
        color: rgb(115,134,120);
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

    .mobile-nav-link {
        display: block;
        padding: 1rem 1rem 1rem 1rem;
        color: #fff;
        text-decoration: none;
        transition: background 0.2s;
    }

    .mobile-nav-link:hover,
    .mobile-nav-link:focus {
        background: rgb(115, 134, 120);
        color: #fff; 
    }
</style>