<script>
  import { onMount } from 'svelte';
  // Responsive layout logic placeholder using ResizeObserver
  let container;
  onMount(() => {
    const observer = new ResizeObserver(entries => {
      for (let entry of entries) {
        console.log('Container resized:', entry.contentRect.width);
      }
    });
    observer.observe(container);
    return () => observer.disconnect();
  });
</script>

<div bind:this={container} class="min-h-screen bg-gray-900 text-gray-100 font-sans p-8">
  <header class="border-b border-gray-700 pb-6 mb-10">
    <h1 class="text-4xl font-light tracking-widest text-amber-500 uppercase">Westin Jazz Nights</h1>
    <p class="text-gray-400 mt-2 italic">A Mid-Week Symphony of Flavours</p>
  </header>

  <main class="grid grid-cols-1 md:grid-cols-2 gap-12">
    <section>
      <h2 class="text-2xl mb-4 font-semibold text-gray-200">The Wednesday Experience</h2>
      <p class="text-gray-300 leading-relaxed">
        Indulge in an exquisite buffet curated by our executive chefs, perfectly paired with the soulful rhythms of Bangkok's finest live jazz ensemble at the Westin Hotel Circle.
      </p>
    </section>

    <section class="bg-gray-800 p-6 rounded-lg border border-gray-700">
      <h2 class="text-xl mb-4 font-semibold text-amber-500">Event Details</h2>
      <ul class="space-y-3">
        <li>Every Wednesday | 19:00 - 22:00</li>
        <li>Westin Hotel Circle, Bangkok</li>
        <li>Buffet & Jazz Package available</li>
      </ul>
      <button class="mt-6 w-full py-3 bg-amber-600 hover:bg-amber-700 text-white rounded transition">
        Reserve Your Table
      </button>
    </section>
  </main>
</div>
