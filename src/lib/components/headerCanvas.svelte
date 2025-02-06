<div
  class="relative w-full md:max-w-[75vw] max-w-[90vw] h-[30vh] md:h-[50vh] mt-12 overflow-hidden rounded-xl"
  style="border-radius: 1rem;"
>
  {#each dashboards as dashboard, i (dashboard.id)}
    <div
      class="absolute inset-0 transition-all duration-500 ease-[cubic-bezier(0.33,1,0.68,1)]"
      style={getSlideStyle(i, activeIndex)}
      in:fly={{ y: 50, duration: 300 }}
      out:fade
    >
      <!-- Zorgt voor de afronding en behoudt de transformaties -->
      <div class="w-full h-full overflow-hidden rounded-xl transition-all duration-300"
           class:blur-sm={i !== activeIndex}
           class:scale-90={i !== activeIndex}>
        <img
          src={dashboard.image}
          alt="Dashboard preview"
          class="w-full h-full object-cover"
        />
      </div>
    </div>
  {/each}
</div>

<script>
  import { fly, fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  const dashboards = [
      { id: 1, image: 'https://pbs.twimg.com/media/F2IC2bWboAAvGOi?format=jpg&name=large' },
      { id: 2, image: 'https://framerusercontent.com/images/a3pzkQHzXU0cJDgsDVDWdbzgfE.webp?scale-down-to=1024' },
      { id: 3, image: 'https://framerusercontent.com/images/QXcqwykmqFqYoAhNvzwR4lk4Jgo.webp?scale-down-to=1024' }
  ];

  let activeIndex = 1; // Start met de middelste slide actief

  function getSlideStyle(index, activeIndex) {
      // Definieer posities en breedtes in percentages (relatief aan de container)
      const positions = {
          left: '0%',
          center: '20%', // actieve slide start op 20% zodat hij gecentreerd is (20% + 60% = 80% totaal, 10% marge aan beide zijden)
          right: '60%'
      };
      
      const widths = {
          active: '60%',   // actieve slide krijgt 60% van de containerbreedte
          inactive: '40%'  // inactieve slides krijgen 40%
      };
      
      const offset = index - activeIndex;
      let position = 'center';
      
      if (offset === -1 || offset === 2) position = 'left';
      if (offset === 1 || offset === -2) position = 'right';

      const width = position === 'center' ? widths.active : widths.inactive;

      return `
          width: ${width};
          left: ${positions[position]};
          z-index: ${position === 'center' ? 20 : 10};
      `;
  }

  function nextSlide() {
      activeIndex = (activeIndex + 1) % dashboards.length;
  }

  // Automatisch elke 3 seconden naar de volgende slide
  onMount(() => {
      const interval = setInterval(nextSlide, 3000);
      return () => clearInterval(interval);
  });
</script>
