<script>
    import '../../app.css';
    import '../../global.css';
    import { Card } from '$lib';
    import { fly } from 'svelte/transition';

    let workCards = [
		{
			title: 'VIA Wiki',
			image: '/work/viawiki.png',
			alt: 'VIA Wiki',
			popupTitle: 'VIA Wiki',
			popupDescription: 'Where I learnt how to code my first website. Here I learnt the basics of React, \
                        and to utilize the frontend tools I have learnt over the past few years.',
            website: "https://www.viawiki.org/projects"
        }
    ]
</script>

<div class="flex flex-col gap-6" in:fly={{ y: 50, duration: 500, delay: 800}} out:fly={{ y: 50, duration: 500 }}>
    <h1 class="poppins-bold text-3xl text-secondary">Work</h1>

    <div class="flex-b justify-center gap-9">
        {#each workCards as workCard}
            <Card {...workCard}/>
        {/each}
    </div>
</div>