<script>
    import '../../app.css';
    import '../../global.css';
    import { fly } from 'svelte/transition';
</script>

<div class="flex flex-col gap-6" in:fly={{ y: 50, duration: 500, delay: 800}} out:fly={{ y: 50, duration: 500 }}>
    <h1 class="poppins-bold text-3xl text-secondary">Contact</h1>
</div>