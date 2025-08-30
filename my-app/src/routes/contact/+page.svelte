<script>
    let statusMessage = '';
    let isLoading = false;

    async function handleSubmit(event) {
        isLoading = true;
        statusMessage = 'Sending...';

        const formData = new FormData(event.target);
        const contactDetails = {
            name: formData.get('name'),
            email: formData.get('email'),
            message: formData.get('message')
        };

        try {
            const response = await fetch('/api/send-email', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({
                    name: contactDetails.name,
                    email: contactDetails.email,
                    message: contactDetails.message
                })
            });

            const result = await response.json();

            if (response.ok) {
                statusMessage = '✅ Success! Your message has been sent.';
                event.target.reset();
            } else {
                statusMessage = `❌ Error: ${result.error || 'Something went wrong.'}`;
            }
        } catch (error) {
            statusMessage = '❌ An error occurred. Please try again.';
            console.error(error);
        } finally {
            isLoading = false;
        }
    }
</script>

<main class="min-h-screen flex flex-col items-center justify-center bg-white px-4 py-16">
    <section class="w-full max-w-md mx-auto flex flex-col items-center">
    <h1 class="text-4xl font-bold mb-8 text-white text-center">Say Hello!</h1>
    {#if statusMessage}
    <div class="text-center mb-6 w-full">{statusMessage}</div>
    {/if}
        <form class="flex flex-col mt-0 mb-8 w-full" on:submit|preventDefault={handleSubmit}>
                    <input required class="contact-input" placeholder="Your Name" type="text" name="name">
                    <input required class="contact-input" placeholder="Your E-mail" type="email" name="email">
                    <textarea name="message" required class="contact-input" placeholder="Your Message"></textarea>
            <button type="submit" class="action-btn h-22 md:h-20 px-4 py-2 flex flex-col items-center justify-center space-y-2">
                <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="mr-2" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="m3 3 3 9-3 9 19-9Z"></path><path d="M6 12h16"></path></svg>
                Submit Message
            </button>
        </form>
        <div class="mt-10 w-full flex flex-col items-center">
            <h2 class="text-lg font-semibold text-white mb-2">Also follow me on :</h2>
            <div class="flex flex-wrap justify-center gap-4 mb-2">
                <a href="https://github.com/ysubbagh" target="_blank" rel="noopener noreferrer" class="action-btn">
                    <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.387.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.084-.729.084-.729 1.205.084 1.84 1.236 1.84 1.236 1.07 1.834 2.809 1.304 3.495.997.108-.775.418-1.305.762-1.605-2.665-.305-5.466-1.334-5.466-5.931 0-1.31.469-2.381 1.236-3.221-.124-.303-.535-1.523.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.553 3.297-1.23 3.297-1.23.653 1.653.242 2.873.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.803 5.624-5.475 5.921.43.372.823 1.102.823 2.222 0 1.606-.014 2.898-.014 3.293 0 .322.218.694.825.576C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
                    GitHub
                </a>
                <a href="mailto:ysubbagh@gmail.com" target="_blank" rel="noopener noreferrer" class="action-btn">
                    <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 2v.01L12 13 4 6.01V6h16zM4 20V8.99l8 7 8-7V20H4z"/></svg>
                    Mail
                </a>
                <a href="https://www.linkedin.com/in/yasmine-subbagh/" target="_blank" rel="noopener noreferrer" class="action-btn">
                    <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.76 0-5 2.24-5 5v14c0 2.76 2.24 5 5 5h14c2.76 0 5-2.24 5-5v-14c0-2.76-2.24-5-5-5zm-11 19h-3v-9h3v9zm-1.5-10.28c-.966 0-1.75-.784-1.75-1.75s.784-1.75 1.75-1.75 1.75.784 1.75 1.75-.784 1.75-1.75 1.75zm15.5 10.28h-3v-4.5c0-1.08-.02-2.47-1.5-2.47-1.5 0-1.73 1.17-1.73 2.38v4.59h-3v-9h2.89v1.23h.04c.4-.76 1.38-1.56 2.84-1.56 3.04 0 3.6 2 3.6 4.59v4.74z"/></svg>
                    LinkedIn
                </a>
            </div>
        </div>
    </section>
</main>

<style>
    .action-btn {
        display: flex;
        align-items: center;
        font-weight: 600;
        border: none;
        background: rgba(255,255,255,0.05);
        padding: 1rem;
        font-size: 0.875rem;
        border-radius: 0.375rem;
        box-shadow: 0 1px 3px 0 rgba(0,0,0,0.1), 0 1px 2px 0 rgba(0,0,0,0.06);
        transition: all 0.3s cubic-bezier(.4,0,.2,1);
        margin-right: 0.5rem;
        gap: 0.5rem;
    }
    .action-btn:hover {
        background: rgb(115,134,120);
        color: #fff;
    }
    .action-btn:active {
        transform: translateY(2px);
    }
    .contact-input {
        padding: 1rem;
        margin-bottom: 0.5rem;
        border: 0;
        border-bottom: 1px solid #e5e7eb;
        background: transparent;
        color: #fff;
        font-size: 1rem;
        transition: border-color 0.5s, box-shadow 0.5s;
    }
    .contact-input:focus {
        outline: none;
        border-bottom: 1.5px solid rgb(115,134,120);
        background: transparent;
        box-shadow: none;
    }
    .contact-input::placeholder {
        color: #9ca3af;
        opacity: 1;
    }
</style>