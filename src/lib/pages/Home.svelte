<script>
    import { fly } from 'svelte/transition';
</script>

<div class="home-wrapper" in:fly="{{ y: -50, duration: 500 }}">
    <h1>JazzRabbit Lite</h1>
</div>

<style>
    .home-wrapper {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
    }
</style>