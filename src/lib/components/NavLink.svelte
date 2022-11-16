<script>
    import { link } from 'svelte-spa-router'
    export let href;
</script>

<a href={href} use:link>
    <slot/>
</a>

<style>
    a {
        width: 25px;
        height: 25px;

        color: rgb(75, 75, 75);
        padding: 30px;
        position: relative;

        transition: color 0.5s;
    }

    .active-page {
        color: rgb(235, 159, 88);
    }

    .current-page:after {
        content: "";
        display: block;
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 3px;

        background-color: rgb(235, 159, 88);
    }
</style>