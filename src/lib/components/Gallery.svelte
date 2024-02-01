<script>
    export let photos;
</script>

<section class="grid md:grid-cols-2 my-12 gap-4 justify-center w-full">
    {#each photos as photo}
            <img src={photo.src} alt={photo.text} class="md:w-[500px] md:h-[500px] w-full">
    {/each}
</section>
