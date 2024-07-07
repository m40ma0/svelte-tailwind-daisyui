<script>
    import '../../app.css';
    import '../../global.css';
    import { fly } from 'svelte/transition';
</script>

<div class="flex flex-col gap-6" in:fly={{ y: 50, duration: 500, delay: 800}} out:fly={{ y: 50, duration: 500 }}>
    <h1 class="poppins-bold text-3xl text-secondary">About Me</h1>

    <div class="flex flex-col gap-3">
        <span>
            I am highly interested in front-end web development and in learning how the web works.
        </span>
        <span>
            I love to create visually stunning interfaces that captivate and engage users, 
            combining aesthetic appeal with intuitive functionality.
        </span>
        <span>
            With a strong foundation in modern web technologies and a keen eye for detail,
            I strive to build responsive, accessible, and interactive designs that not only meet but exceed user expectations.
        </span>
    </div>
</div>