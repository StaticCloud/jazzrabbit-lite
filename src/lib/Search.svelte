<script lang="ts">

</script>

<div>
    <form on:submit|preventDefault={() => console.log('hello!')}>
        <label for="music-search">Search for music:</label>
        <input id="music-search"/>
        <button type="submit">Submit</button>
    </form>
</div>