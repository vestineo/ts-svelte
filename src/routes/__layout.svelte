<script context="module">
  export const load = ({ url }) => {
    const currentRoute = url.pathname

    return {
      props: {
        currentRoute
      }
    }
  }
</script>
<script>
	import Header from '$lib/components/Header.svelte';
	import '$lib/styles/style.css';
	import { fade } from 'svelte/transition'

  export let currentRoute
</script>

<Header />
<footer>
	<p><a href='/'>Back to Home</a></p>
</footer>

{#key currentRoute}
  <main in:fade={{ duration: 150, delay: 150 }} out:fade={{ duration: 150 }}>
    <slot />
  </main>
{/key}
