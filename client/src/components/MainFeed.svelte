<main class="feed">
    {#each Array.from({length:10}) as item}
        <div class="project">
            Lorem ipsum dolor sit amet.
        </div>
    {/each}
</main>

<style>
    .feed {
        grid-column-start: 2;
    }

    .project {
        padding: 3rem 0.5rem;
        margin-bottom: 0.5rem;

        border:2px solid white;
        border-radius: 5px;
    }
</style>