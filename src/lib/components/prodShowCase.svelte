<script>
        import dash1 from "$lib/img/dash1.avif"
        import dash2 from "$lib/img/dash2.avif"
        import dash3 from "$lib/img/dash3.avif"
        import dash4 from "$lib/img/dash4.avif"

        import { onMount } from 'svelte';

    const section1 = `

        <h3 class="text-2xl font-bold">Een directe overzicht van je financiën</h3>
        <p>Krijg volledig inzicht in je financiële prestaties. Volg netto-omzet, bekijk trends en maak onderbouwde beslissingen om je omzet te verbeteren.</p>
        <div class="flex gap-4 mt-4 myText">
            <a class="bg-zinc-900 p-2 rounded-xl flex" href="/">
                <svg class="mr-1" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
                    <path fill="currentColor" fill-rule="evenodd" d="M22 12c0 5.523-4.477 10-10 10c-1.6 0-3.112-.376-4.452-1.044a1.63 1.63 0 0 0-1.149-.133l-2.226.596a1.3 1.3 0 0 1-1.591-1.592l.595-2.226a1.63 1.63 0 0 0-.134-1.148A9.96 9.96 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10M12 7.25a.75.75 0 0 1 .75.75v.01c1.089.275 2 1.133 2 2.323a.75.75 0 0 1-1.5 0c0-.384-.426-.916-1.25-.916s-1.25.532-1.25.916s.426.917 1.25.917c1.385 0 2.75.96 2.75 2.417c0 1.19-.911 2.049-2 2.323V16a.75.75 0 0 1-1.5 0v-.01c-1.089-.274-2-1.133-2-2.323a.75.75 0 0 1 1.5 0c0 .384.426.916 1.25.916s1.25-.532 1.25-.916s-.426-.917-1.25-.917c-1.385 0-2.75-.96-2.75-2.417c0-1.19.911-2.048 2-2.323V8a.75.75 0 0 1 .75-.75" clip-rule="evenodd" />
                </svg>
                inkomsten
            </a>
            <a class="bg-zinc-900 p-2 rounded-xl flex" href="/">
                <svg class="mr-1" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
                    <path fill="currentColor" d="M6.26 21.388H6c-.943 0-1.414 0-1.707-.293C4 20.804 4 20.332 4 19.389v-1.112c0-.518 0-.777.133-1.009s.334-.348.736-.582c2.646-1.539 6.403-2.405 8.91-.91q.253.151.45.368a1.49 1.49 0 0 1-.126 2.134a1 1 0 0 1-.427.24q.18-.021.345-.047c.911-.145 1.676-.633 2.376-1.162l1.808-1.365a1.89 1.89 0 0 1 2.22 0c.573.433.749 1.146.386 1.728c-.423.678-1.019 1.545-1.591 2.075s-1.426 1.004-2.122 1.34c-.772.373-1.624.587-2.491.728c-1.758.284-3.59.24-5.33-.118a15 15 0 0 0-3.017-.308m.326-18.803c-.367.367-.504.873-.555 1.664A2.25 2.25 0 0 0 8.25 2.03c-.79.052-1.297.189-1.664.556m10.828 0c-.367-.367-.873-.504-1.664-.555a2.25 2.25 0 0 0 2.22 2.219c-.052-.79-.189-1.297-.556-1.664m0 6.828c-.367.367-.873.504-1.664.555a2.25 2.25 0 0 1 2.22-2.219c-.052.79-.189 1.297-.556 1.664m-10.828 0c.367.367.873.504 1.664.555A2.25 2.25 0 0 0 6.03 7.75c.052.79.189 1.297.556 1.664" />
                    <path fill="currentColor" fill-rule="evenodd" d="M6 5.75A3.75 3.75 0 0 0 9.75 2h4.5A3.75 3.75 0 0 0 18 5.75v.5A3.75 3.75 0 0 0 14.25 10h-4.5A3.75 3.75 0 0 0 6 6.25zM12 7a1 1 0 1 0 0-2a1 1 0 0 0 0 2" clip-rule="evenodd" />
                </svg>
                uitgaven
            </a>
            <a class="bg-zinc-900 p-2 rounded-xl flex" href="/">
                <svg class="mr-1" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
                    <path fill="currentColor" fill-rule="evenodd" d="M2 1.25a.75.75 0 0 0 0 1.5h2v7.75c0 3.064 0 4.596 1.004 5.548s2.62.952 5.853.952h.393v3.537l-1.585.792a.75.75 0 1 0 .67 1.342L12 21.839l1.665.832a.75.75 0 1 0 .67-1.342l-1.585-.793V17h.393c3.232 0 4.849 0 5.853-.952S20 13.564 20 10.5V2.75h2a.75.75 0 0 0 0-1.5zm13.53 6.72a.75.75 0 0 1 0 1.06l-1.317 1.318a5 5 0 0 1-.452.416a1.24 1.24 0 0 1-.761.279a1.24 1.24 0 0 1-.761-.279a5 5 0 0 1-.452-.416l-.61-.61L11 9.561l-.177.175L9.53 11.03a.75.75 0 1 1-1.06-1.06l1.317-1.318c.145-.145.302-.302.452-.416A1.24 1.24 0 0 1 11 7.957c.334 0 .585.145.761.279c.15.114.307.271.452.416l.61.61l.177.176l.177-.175L14.47 7.97a.75.75 0 0 1 1.06 0" clip-rule="evenodd" />
                </svg>
                KPI's
            </a>
            <a class="bg-zinc-900 p-2 rounded-xl flex" href="/">
                <svg class="mr-1" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
                    <path fill="currentColor" fill-rule="evenodd" d="M2 1.25a.75.75 0 0 0 0 1.5h2v7.75c0 3.064 0 4.596 1.004 5.548s2.62.952 5.853.952h.393v3.537l-1.585.792a.75.75 0 1 0 .67 1.342L12 21.839l1.665.832a.75.75 0 1 0 .67-1.342l-1.585-.793V17h.393c3.232 0 4.849 0 5.853-.952S20 13.564 20 10.5V2.75h2a.75.75 0 0 0 0-1.5zm13.53 6.72a.75.75 0 0 1 0 1.06l-1.317 1.318a5 5 0 0 1-.452.416a1.24 1.24 0 0 1-.761.279a1.24 1.24 0 0 1-.761-.279a5 5 0 0 1-.452-.416l-.61-.61L11 9.561l-.177.175L9.53 11.03a.75.75 0 1 1-1.06-1.06l1.317-1.318c.145-.145.302-.302.452-.416A1.24 1.24 0 0 1 11 7.957c.334 0 .585.145.761.279c.15.114.307.271.452.416l.61.61l.177.176l.177-.175L14.47 7.97a.75.75 0 0 1 1.06 0" clip-rule="evenodd" />
                </svg>
                statistieken
            </a>
        </div>
        <button class="mt-6 rounded-full px-7 py-3 myBtn text-black" aria-label="s">
            Direct Contact
        </button>
    `



  let currentImage = dash1;
  let stickyImageRef;
  let sections = [
    { image: dash1, content: section1 },
    { image: dash2, content: 'Section 2' },
    { image: dash3, content: 'Section 3' },
    { image: dash4, content: 'Section 4' }
  ];

  // Preload images on mount
  onMount(() => {
    // Image preloading
    sections.forEach(({ image }) => new Image().src = image);
    
    // Intersection Observer setup
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            currentImage = entry.target.dataset.image;
          }
        });
      },
      { threshold: 0.5 }
    );

    // Observe all sections
    document.querySelectorAll('[data-section]').forEach(section => {
      observer.observe(section);
    });

    return () => observer.disconnect();
  });
</script>
<!-- <div class="flex flex-wrap w-full gap-12 mt-16">
    <div class="flex-1 rounded-2xl">
        <img src={dash1} alt="" class="rounded-2xl" />
    </div>
    <div class="flex flex-col flex-1 justify-center">
        <h3 class="text-2xl font-bold">Een directe overzicht van je financiën</h3>
        <p>Krijg volledig inzicht in je financiële prestaties. Volg netto-omzet, bekijk trends en maak onderbouwde beslissingen om je omzet te verbeteren.</p>
        <div class="flex gap-4 mt-4 myText">
            <a class="bg-zinc-900 p-2 rounded-xl flex" href="/">
                <svg class="mr-1" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
                    <path fill="currentColor" fill-rule="evenodd" d="M22 12c0 5.523-4.477 10-10 10c-1.6 0-3.112-.376-4.452-1.044a1.63 1.63 0 0 0-1.149-.133l-2.226.596a1.3 1.3 0 0 1-1.591-1.592l.595-2.226a1.63 1.63 0 0 0-.134-1.148A9.96 9.96 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10M12 7.25a.75.75 0 0 1 .75.75v.01c1.089.275 2 1.133 2 2.323a.75.75 0 0 1-1.5 0c0-.384-.426-.916-1.25-.916s-1.25.532-1.25.916s.426.917 1.25.917c1.385 0 2.75.96 2.75 2.417c0 1.19-.911 2.049-2 2.323V16a.75.75 0 0 1-1.5 0v-.01c-1.089-.274-2-1.133-2-2.323a.75.75 0 0 1 1.5 0c0 .384.426.916 1.25.916s1.25-.532 1.25-.916s-.426-.917-1.25-.917c-1.385 0-2.75-.96-2.75-2.417c0-1.19.911-2.048 2-2.323V8a.75.75 0 0 1 .75-.75" clip-rule="evenodd" />
                </svg>
                inkomsten
            </a>
            <a class="bg-zinc-900 p-2 rounded-xl flex" href="/">
                <svg class="mr-1" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
                    <path fill="currentColor" d="M6.26 21.388H6c-.943 0-1.414 0-1.707-.293C4 20.804 4 20.332 4 19.389v-1.112c0-.518 0-.777.133-1.009s.334-.348.736-.582c2.646-1.539 6.403-2.405 8.91-.91q.253.151.45.368a1.49 1.49 0 0 1-.126 2.134a1 1 0 0 1-.427.24q.18-.021.345-.047c.911-.145 1.676-.633 2.376-1.162l1.808-1.365a1.89 1.89 0 0 1 2.22 0c.573.433.749 1.146.386 1.728c-.423.678-1.019 1.545-1.591 2.075s-1.426 1.004-2.122 1.34c-.772.373-1.624.587-2.491.728c-1.758.284-3.59.24-5.33-.118a15 15 0 0 0-3.017-.308m.326-18.803c-.367.367-.504.873-.555 1.664A2.25 2.25 0 0 0 8.25 2.03c-.79.052-1.297.189-1.664.556m10.828 0c-.367-.367-.873-.504-1.664-.555a2.25 2.25 0 0 0 2.22 2.219c-.052-.79-.189-1.297-.556-1.664m0 6.828c-.367.367-.873.504-1.664.555a2.25 2.25 0 0 1 2.22-2.219c-.052.79-.189 1.297-.556 1.664m-10.828 0c.367.367.873.504 1.664.555A2.25 2.25 0 0 0 6.03 7.75c.052.79.189 1.297.556 1.664" />
                    <path fill="currentColor" fill-rule="evenodd" d="M6 5.75A3.75 3.75 0 0 0 9.75 2h4.5A3.75 3.75 0 0 0 18 5.75v.5A3.75 3.75 0 0 0 14.25 10h-4.5A3.75 3.75 0 0 0 6 6.25zM12 7a1 1 0 1 0 0-2a1 1 0 0 0 0 2" clip-rule="evenodd" />
                </svg>
                uitgaven
            </a>
            <a class="bg-zinc-900 p-2 rounded-xl flex" href="/">
                <svg class="mr-1" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
                    <path fill="currentColor" fill-rule="evenodd" d="M2 1.25a.75.75 0 0 0 0 1.5h2v7.75c0 3.064 0 4.596 1.004 5.548s2.62.952 5.853.952h.393v3.537l-1.585.792a.75.75 0 1 0 .67 1.342L12 21.839l1.665.832a.75.75 0 1 0 .67-1.342l-1.585-.793V17h.393c3.232 0 4.849 0 5.853-.952S20 13.564 20 10.5V2.75h2a.75.75 0 0 0 0-1.5zm13.53 6.72a.75.75 0 0 1 0 1.06l-1.317 1.318a5 5 0 0 1-.452.416a1.24 1.24 0 0 1-.761.279a1.24 1.24 0 0 1-.761-.279a5 5 0 0 1-.452-.416l-.61-.61L11 9.561l-.177.175L9.53 11.03a.75.75 0 1 1-1.06-1.06l1.317-1.318c.145-.145.302-.302.452-.416A1.24 1.24 0 0 1 11 7.957c.334 0 .585.145.761.279c.15.114.307.271.452.416l.61.61l.177.176l.177-.175L14.47 7.97a.75.75 0 0 1 1.06 0" clip-rule="evenodd" />
                </svg>
                KPI's
            </a>
            <a class="bg-zinc-900 p-2 rounded-xl flex" href="/">
                <svg class="mr-1" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
                    <path fill="currentColor" fill-rule="evenodd" d="M2 1.25a.75.75 0 0 0 0 1.5h2v7.75c0 3.064 0 4.596 1.004 5.548s2.62.952 5.853.952h.393v3.537l-1.585.792a.75.75 0 1 0 .67 1.342L12 21.839l1.665.832a.75.75 0 1 0 .67-1.342l-1.585-.793V17h.393c3.232 0 4.849 0 5.853-.952S20 13.564 20 10.5V2.75h2a.75.75 0 0 0 0-1.5zm13.53 6.72a.75.75 0 0 1 0 1.06l-1.317 1.318a5 5 0 0 1-.452.416a1.24 1.24 0 0 1-.761.279a1.24 1.24 0 0 1-.761-.279a5 5 0 0 1-.452-.416l-.61-.61L11 9.561l-.177.175L9.53 11.03a.75.75 0 1 1-1.06-1.06l1.317-1.318c.145-.145.302-.302.452-.416A1.24 1.24 0 0 1 11 7.957c.334 0 .585.145.761.279c.15.114.307.271.452.416l.61.61l.177.176l.177-.175L14.47 7.97a.75.75 0 0 1 1.06 0" clip-rule="evenodd" />
                </svg>
                statistieken
            </a>
        </div>
        <button class="mt-6 rounded-full px-7 py-3 myBtn text-black" aria-label="s">
            Direct Contact
        </button>
    </div>
</div> -->
<div class="flex flex-col mt-20">
    <div class="sticky-container">
        {#if currentImage}
            <div class="max-w-[50%]">
                <img 
                  src={currentImage} 
                  alt="Sticky content"
                  class="rounded-2xl" 
                  transition:fade={{ duration: 300 }}
                />
        </div>
        {/if}
      </div>
      {#each sections as section, i}
      <div class="flex">
        <div class="flex-1"></div>
        <section 
          data-section 
          data-image={section.image}
          class="scroll-section flex-1 pl-11"
        >
        <div class="flex flex-col justify-center">{@html section.content}</div>
        </section>
        </div>
        {/each}
</div>



<style>
    .myText {
        color: rgb(234, 168, 121);
    }
    .myBtn {
        background-color: rgb(234, 168, 121);
    }
    .sticky-container {
    position: sticky;
    top: 0;
    z-index: 100;
    height: 100vh; /* Maintain viewport height */
  }

  img {
    width: 100%;
    height: auto;
    transition: opacity 0.3s ease;
  }

  .scroll-section {
    min-height: 100vh;
    padding: 2rem;
    scroll-snap-align: start;
  }
</style>