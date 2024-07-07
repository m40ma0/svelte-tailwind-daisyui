<script>
	import '../app.css';
	import '../global.css';
	import { fly } from 'svelte/transition';
  </script>
  
  <div class="navbar bg-base-100 poppins-semibold">
	<div class="flex-1">
	  <a href="/" class="btn btn-ghost text-xl">Maomao</a>
	</div>
	<div class="flex-none">
	  <ul class="menu menu-horizontal px-1">
		<li><a href="/about">About</a></li>
		<li><a href="/work">Work</a></li>
		<li><a href="/contact">Contact</a></li>
	  </ul>
	</div>
  </div>
  
  <!-- Apply the transition directly to a wrapping div -->
  <div class="poppins-regular mx-20 my-8" in:fly={{ x: -400, duration: 2000 }} out:fly={{ x: 400, duration: 2000 }}>
	<slot />
  </div>
  