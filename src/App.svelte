<script lang="ts">
	import Tailwindcss from './Tailwindcss.svelte';
	import Header from './components/Header.svelte';
import Counter from './components/Counter.svelte';
</script>

<Tailwindcss />
<Header />
<main class="pt-16">
	<div class="container mx-auto px-6 my-4">
	 <Counter />
	</div>
</main>