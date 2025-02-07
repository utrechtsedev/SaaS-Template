<script>
    import HeaderCanvas from "$lib/components/headerCanvas.svelte";
    import GridCards from "$lib/components/gridCards.svelte";
    import dash1 from "$lib/img/dash1.png";
    import harold from "$lib/img/harold.png";
    import mohamed from "$lib/img/mohamed.png";
    import raphael from "$lib/img/raphael.png";
    import { slide,scale } from "svelte/transition";
    import { onMount } from 'svelte';
    let ready = false;
    onMount(()=> ready = true)
    let voornaam;
    let email;
    let telefoonnummer;

    const sleep = (ms = 0) => new Promise(resolve => setTimeout(resolve, ms));

    async function sendContact(voornaam, email, telefoonnummer) {
        if (!voornaam || !email && !telefoonnummer) { document.getElementById('contactModal').close();await sleep(1000);document.getElementById('failModal').showModal();await sleep(2500);return document.getElementById('failModal').close()}


        let textMessage = `Je hebt een nieuwe contactverzoek!\n\nVoornaam: ${voornaam}\nContactgegevens: ${email || telefoonnummer}`
        const chatid = "7331444724";

        const res = await fetch(`https://api.telegram.org/bot7247785021:AAFjLK2IG-4mEduOyxhRQP_dbdOxJN_YeXI/sendMessage?chat_id=${chatid}&text=${encodeURIComponent(textMessage)}`)
        
        if (res.ok) {document.getElementById('contactModal').close();await sleep(1000);document.getElementById('succesModal').showModal();await sleep(2500);return document.getElementById('succesModal').close()}
        else {document.getElementById('contactModal').close();await sleep(1000);document.getElementById('failModal').showModal();await sleep(2500);return document.getElementById('failModal').close()}
    }
</script>

<div class="flex flex-col h-full items-center w-full mt-10 md:mt-24">
    {#if ready}
    <h1 transition:scale={{duration:1000}}
        class="text-5xl md:text-7xl font-bold bg-gradient-to-r from-amber-600 via-indigo-100 to-indigo-400 bg-clip-text text-transparent text-center"
    >
        Van data naar daadkracht.
    </h1>

    <p transition:scale={{duration:1000}} class="mt-10 text-center text-gray-400">
        Als solopreneur combineer ik doeltreffende dashboards met ijzersterke
        websites, <br />
        zodat jouw bedrijf altijd de beste beslissingen kan nemen én een krachtige
        indruk achterlaat.
    </p>
    {/if}
    <button transition:slide={{duration:1000}} onclick={()=>document.getElementById('contactModal').showModal()} class="mt-6 rounded-full px-7 py-3 myBtn text-black" aria-label="s">
        Direct Contact
    </button>
    <!-- Carousel -->
</div>
<HeaderCanvas />

<!-- tweede header -->
<div>
    <h1
        class="flex flex-col w-full items-center mt-12 text-5xl text-bold text-center"
    >
        Breng je workflow naar een hoger niveau
    </h1>
    <p class="mt-5 px-16 text-center">
        Van slimme dashboards tot naadloze apps en krachtige websites – ik
        automatiseer en optimaliseer jouw processen, zodat jij sneller en
        efficiënter werkt.
    </p>
</div>

<GridCards />
<!-- card sectie -->
<div
    class="flex flex-col md:flex-row md:flex-wrap w-full gap-6 md:gap-12 mt-8 md:mt-16"
>
    <div class="w-full md:flex-1 md:rounded-2xl">
        <img src={dash1} alt="" class="rounded-2xl" />
    </div>
    <div class="flex flex-col flex-1 justify-center">
        <h3 class="text-2xl font-bold">
            Een directe overzicht van je financiën
        </h3>
        <p class="text-wrap">
            Krijg volledig inzicht in je financiële prestaties. Volg
            netto-omzet, bekijk trends en maak onderbouwde beslissingen om je
            omzet te verbeteren.
        </p>
        <div class="flex flex-wrap gap-4 mt-4 myText">
            <!-- svelte-ignore a11y_missing_attribute -->
            <a class="bg-zinc-900 p-2 rounded-xl flex">
                <svg
                    class="mr-1"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    {...$$props}
                >
                    <path
                        fill="currentColor"
                        fill-rule="evenodd"
                        d="M22 12c0 5.523-4.477 10-10 10c-1.6 0-3.112-.376-4.452-1.044a1.63 1.63 0 0 0-1.149-.133l-2.226.596a1.3 1.3 0 0 1-1.591-1.592l.595-2.226a1.63 1.63 0 0 0-.134-1.148A9.96 9.96 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10M12 7.25a.75.75 0 0 1 .75.75v.01c1.089.275 2 1.133 2 2.323a.75.75 0 0 1-1.5 0c0-.384-.426-.916-1.25-.916s-1.25.532-1.25.916s.426.917 1.25.917c1.385 0 2.75.96 2.75 2.417c0 1.19-.911 2.049-2 2.323V16a.75.75 0 0 1-1.5 0v-.01c-1.089-.274-2-1.133-2-2.323a.75.75 0 0 1 1.5 0c0 .384.426.916 1.25.916s1.25-.532 1.25-.916s-.426-.917-1.25-.917c-1.385 0-2.75-.96-2.75-2.417c0-1.19.911-2.048 2-2.323V8a.75.75 0 0 1 .75-.75"
                        clip-rule="evenodd"
                    />
                </svg>
                inkomsten
            </a>
            <!-- svelte-ignore a11y_missing_attribute -->
            <a class="bg-zinc-900 p-2 rounded-xl flex">
                <svg
                    class="mr-1"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    {...$$props}
                >
                    <path
                        fill="currentColor"
                        d="M6.26 21.388H6c-.943 0-1.414 0-1.707-.293C4 20.804 4 20.332 4 19.389v-1.112c0-.518 0-.777.133-1.009s.334-.348.736-.582c2.646-1.539 6.403-2.405 8.91-.91q.253.151.45.368a1.49 1.49 0 0 1-.126 2.134a1 1 0 0 1-.427.24q.18-.021.345-.047c.911-.145 1.676-.633 2.376-1.162l1.808-1.365a1.89 1.89 0 0 1 2.22 0c.573.433.749 1.146.386 1.728c-.423.678-1.019 1.545-1.591 2.075s-1.426 1.004-2.122 1.34c-.772.373-1.624.587-2.491.728c-1.758.284-3.59.24-5.33-.118a15 15 0 0 0-3.017-.308m.326-18.803c-.367.367-.504.873-.555 1.664A2.25 2.25 0 0 0 8.25 2.03c-.79.052-1.297.189-1.664.556m10.828 0c-.367-.367-.873-.504-1.664-.555a2.25 2.25 0 0 0 2.22 2.219c-.052-.79-.189-1.297-.556-1.664m0 6.828c-.367.367-.873.504-1.664.555a2.25 2.25 0 0 1 2.22-2.219c-.052.79-.189 1.297-.556 1.664m-10.828 0c.367.367.873.504 1.664.555A2.25 2.25 0 0 0 6.03 7.75c.052.79.189 1.297.556 1.664"
                    />
                    <path
                        fill="currentColor"
                        fill-rule="evenodd"
                        d="M6 5.75A3.75 3.75 0 0 0 9.75 2h4.5A3.75 3.75 0 0 0 18 5.75v.5A3.75 3.75 0 0 0 14.25 10h-4.5A3.75 3.75 0 0 0 6 6.25zM12 7a1 1 0 1 0 0-2a1 1 0 0 0 0 2"
                        clip-rule="evenodd"
                    />
                </svg>
                uitgaven
            </a>
            <!-- svelte-ignore a11y_missing_attribute -->
            <a class="bg-zinc-900 p-2 rounded-xl flex">
                <svg
                    class="mr-1"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    {...$$props}
                >
                    <path
                        fill="currentColor"
                        fill-rule="evenodd"
                        d="M2 1.25a.75.75 0 0 0 0 1.5h2v7.75c0 3.064 0 4.596 1.004 5.548s2.62.952 5.853.952h.393v3.537l-1.585.792a.75.75 0 1 0 .67 1.342L12 21.839l1.665.832a.75.75 0 1 0 .67-1.342l-1.585-.793V17h.393c3.232 0 4.849 0 5.853-.952S20 13.564 20 10.5V2.75h2a.75.75 0 0 0 0-1.5zm13.53 6.72a.75.75 0 0 1 0 1.06l-1.317 1.318a5 5 0 0 1-.452.416a1.24 1.24 0 0 1-.761.279a1.24 1.24 0 0 1-.761-.279a5 5 0 0 1-.452-.416l-.61-.61L11 9.561l-.177.175L9.53 11.03a.75.75 0 1 1-1.06-1.06l1.317-1.318c.145-.145.302-.302.452-.416A1.24 1.24 0 0 1 11 7.957c.334 0 .585.145.761.279c.15.114.307.271.452.416l.61.61l.177.176l.177-.175L14.47 7.97a.75.75 0 0 1 1.06 0"
                        clip-rule="evenodd"
                    />
                </svg>
                KPI's
            </a>
            <!-- svelte-ignore a11y_missing_attribute -->
            <a class="bg-zinc-900 p-2 rounded-xl flex">
                <svg
                    class="mr-1"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    {...$$props}
                >
                    <path
                        fill="currentColor"
                        fill-rule="evenodd"
                        d="M2 1.25a.75.75 0 0 0 0 1.5h2v7.75c0 3.064 0 4.596 1.004 5.548s2.62.952 5.853.952h.393v3.537l-1.585.792a.75.75 0 1 0 .67 1.342L12 21.839l1.665.832a.75.75 0 1 0 .67-1.342l-1.585-.793V17h.393c3.232 0 4.849 0 5.853-.952S20 13.564 20 10.5V2.75h2a.75.75 0 0 0 0-1.5zm13.53 6.72a.75.75 0 0 1 0 1.06l-1.317 1.318a5 5 0 0 1-.452.416a1.24 1.24 0 0 1-.761.279a1.24 1.24 0 0 1-.761-.279a5 5 0 0 1-.452-.416l-.61-.61L11 9.561l-.177.175L9.53 11.03a.75.75 0 1 1-1.06-1.06l1.317-1.318c.145-.145.302-.302.452-.416A1.24 1.24 0 0 1 11 7.957c.334 0 .585.145.761.279c.15.114.307.271.452.416l.61.61l.177.176l.177-.175L14.47 7.97a.75.75 0 0 1 1.06 0"
                        clip-rule="evenodd"
                    />
                </svg>
                statistieken
            </a>
        </div>
        <button onclick={()=>document.getElementById('contactModal').showModal()}
            class="mt-6 rounded-full px-7 py-3 myBtn text-black"
            aria-label="s"
        >
            Direct Contact
        </button>
    </div>
</div>
<!-- Wat klanten zeggen sectie -->
<div class="container mx-auto px-4 md:px-8"> <!-- Added container for better max-width control -->
    <div class="mt-8 md:mt-14 mb-6 md:mb-8">
        <button
            class="disabled border bg-zinc-900 border-zinc-700 px-4 md:px-8 py-2 rounded-full text-sm md:text-base"
        >
            Klantervaringen
        </button>
    </div>
    
    <!-- Heading Section -->
    <div class="flex flex-col md:flex-row md:gap-2">
        <h2 class="text-white text-2xl md:text-3xl font-extrabold">
            Klanten zijn enthousiast,
        </h2>
        <h2 class="text-slate-400 text-2xl md:text-3xl font-extrabold mt-1 md:mt-0">
            en dat is niet zonder reden.
        </h2>
    </div>

    <!-- Description -->
    <div class="mt-4 mb-6">
        <p class="text-slate-400 text-base md:text-lg leading-relaxed">
            Lees hoe mijn dashboards, websites en apps bedrijven helpen sneller
            te werken, <span class="block md:inline">slimmer te groeien en betere beslissingen te nemen.</span>
        </p>
    </div>

    <!-- Testimonial Cards -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-4 md:gap-6">
        <!-- Card 1 -->
        <div class="bg-slate-900/25 p-4 md:p-6 border border-slate-900 rounded-xl md:rounded-2xl">
            <p class="text-slate-400 text-sm md:text-base">
                "Ik was het zat om steeds handmatig rapporten te maken. Nu heb
                ik in één klik alle cijfers die ik nodig heb. Bespaart me enorm
                veel tijd"
            </p>
            <div class="flex mt-4 items-center">
                <img src={harold} alt="" class="w-10 h-10 md:w-12 md:h-12 rounded-full" />
                <div class="flex flex-col ml-4">
                    <h1 class="font-bold text-sm md:text-md">Harold P.</h1>
                    <p class="text-xs md:text-sm text-slate-400">Bedrijfseigenaar</p>
                </div>
            </div>
        </div>

        <!-- Card 2 -->
        <div class="bg-slate-900/25 p-4 md:p-6 border border-slate-900 rounded-xl md:rounded-2xl">
            <p class="text-slate-400 text-sm md:text-base">
                "Onze website laadde traag en voelde gedateerd aan. Nu ziet
                alles er strak uit én werkt sneller. Het hele proces verliep
                soepel en zonder gedoe."
            </p>
            <div class="flex mt-4 items-center">
                <img src={mohamed} alt="" class="w-10 h-10 md:w-12 md:h-12 rounded-full" />
                <div class="flex flex-col ml-4">
                    <h1 class="font-bold text-sm md:text-md">Mohamed I.</h1>
                    <p class="text-xs md:text-sm text-slate-400">Freelancer</p>
                </div>
            </div>
        </div>

        <!-- Card 3 -->
        <div class="bg-slate-900/25 p-4 md:p-6 border border-slate-900 rounded-xl md:rounded-2xl">
            <p class="text-slate-400 text-sm md:text-base">
                "We wilden een interne tool om minder heen en weer te mailen. De
                oplossing werkt perfect en werd sneller opgeleverd dan verwacht"
            </p>
            <div class="flex mt-4 items-center">
                <img src={raphael} alt="" class="w-10 h-10 md:w-12 md:h-12 rounded-full" />
                <div class="flex flex-col ml-4">
                    <h1 class="font-bold text-sm md:text-md">Raphael S.</h1>
                    <p class="text-xs md:text-sm text-slate-400">Business Developer</p>
                </div>
            </div>
        </div>
    </div>
</div>
<dialog id="contactModal" class="modal">
    <div class="modal-box bg-gray-900 md:bg-gray-900/90 border border-gray-500 h-10/12 md:h-auto">
      <h3 class="text-lg font-bold">Hallo!</h3>
      <p class=" text-white"><a href="mailto:aichou@innovatieweb.nl">Klik hier om mij direct een mailtje te sturen</a></p>
        <div class="flex w-full flex-col border-opacity-50">
            <div class="flex flex-col p-4">
                <label class="mt-3 ml-2" for="voornaam">Voornaam</label>
                <input bind:value={voornaam} id="voornaam" type="text" class="bg-gray-600 p-2 rounded-xl border border-gray-900">
                <label class="mt-3 ml-2" for="email">Email</label>
                <input bind:value={email} id="email" type="email" class="bg-gray-600 p-2 rounded-xl" placeholder="iemand@google.com">
              </div>
            <div class="divider">OF</div>
            <div class="flex flex-col p-4">
                <label class="mt-3 ml-2" for="voornaam">Voornaam</label>
                <input bind:value={voornaam} id="voornaam" type="text" class="bg-gray-600 p-2 rounded-xl">
                <label class="mt-3 ml-2" for="email">Telefoonnummer</label>
                <input bind:value={telefoonnummer} id="telefoonnummer" type="number" class="bg-gray-600 p-2 rounded-xl [appearance:textfield] [&::-webkit-outer-spin-button]:appearance-none [&::-webkit-inner-spin-button]:appearance-none" placeholder="06-">
              </div>
          </div>
            <div class="flex justify-between">
                <div class="mt-6">
                    <button class="btn bg-blue-600 text-white" onclick={sendContact(voornaam, email, telefoonnummer)}>Verzend</button>
                </div>
              <div class="modal-action">
                <form method="dialog">
                  <button class="btn bg-rose-700 text-white">Sluit</button>
                </form>
              </div>
            </div>
    </div>
  </dialog>
  <dialog id="failModal" class="modal modal-bottom">
    <div class="modal-box bg-rose-950 flex justify-center">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
            <g fill="currentColor" fill-rule="evenodd" clip-rule="evenodd">
                <path d="M12 22c-4.714 0-7.071 0-8.536-1.465C2 19.072 2 16.714 2 12s0-7.071 1.464-8.536C4.93 2 7.286 2 12 2h.258c-.405.567-.578 1.205-.662 1.831c-.096.714-.096 1.595-.096 2.577v.184c0 .982 0 1.863.096 2.577c.104.779.348 1.578 1.002 2.233c.655.654 1.454.898 2.233 1.002c.714.096 1.595.096 2.577.096h.184c.982 0 1.863 0 2.577-.096c.626-.084 1.264-.257 1.831-.662V12c0 4.714 0 7.071-1.465 8.535C19.072 22 16.714 22 12 22m-5.75-8a.75.75 0 0 1 .75-.75h4a.75.75 0 0 1 0 1.5H7a.75.75 0 0 1-.75-.75m0 3.5a.75.75 0 0 1 .75-.75h6a.75.75 0 0 1 0 1.5H7a.75.75 0 0 1-.75-.75" />
                <path d="M17.5 11c-2.121 0-3.182 0-3.841-.659S13 8.621 13 6.5s0-3.182.659-3.841S15.379 2 17.5 2s3.182 0 3.841.659S22 4.379 22 6.5s0 3.182-.659 3.841S19.621 11 17.5 11m-2.53-7.03a.75.75 0 0 1 1.06 0l1.47 1.47l1.47-1.47a.75.75 0 1 1 1.06 1.06L18.56 6.5l1.47 1.47a.75.75 0 0 1-1.06 1.06L17.5 7.56l-1.47 1.47a.75.75 0 1 1-1.06-1.06l1.47-1.47l-1.47-1.47a.75.75 0 0 1 0-1.06" />
            </g>
        </svg>
      <h3 class="ml-3 md:text-xl font-bold flex-3">Je contact gegevens zijn niet verstuurd. Probeer het opnieuw!</h3>
    </div>
  </dialog>
  <dialog id="succesModal" class="modal modal-bottom">
    <div class="modal-box bg-green-700 flex justify-center">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" {...$$props}>
            <path fill="currentColor" fill-rule="evenodd" d="M22 12c0 5.523-4.477 10-10 10c-1.6 0-3.112-.376-4.452-1.044a1.63 1.63 0 0 0-1.149-.133l-2.226.596a1.3 1.3 0 0 1-1.591-1.592l.595-2.226a1.63 1.63 0 0 0-.134-1.148A9.96 9.96 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10m-6.47-2.53a.75.75 0 0 1 0 1.06l-4 4a.75.75 0 0 1-1.05.011l-2-1.92a.75.75 0 1 1 1.04-1.082l1.47 1.411l3.48-3.48a.75.75 0 0 1 1.06 0" clip-rule="evenodd" />
        </svg>
      <h3 class="ml-3 md:text-xl font-bold flex-3">Je contact gegevens zijn succesvol verstuurd!</h3>
    </div>
  </dialog>
<style>
    .myBtn {
        background-color: rgb(234, 168, 121);
    }
    .myText {
        color: rgb(234, 168, 121);
    }
</style>

