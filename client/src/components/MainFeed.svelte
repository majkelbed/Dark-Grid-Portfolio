<script>
    import { onMount } from "svelte";
    import { INTERSECTED_SECTION } from '../stores/HomePage.js';

    onMount(() => {
        const options = { }
        const handler = ([{isIntersecting, target}]) => {
            if(isIntersecting) {
                const { section } = target.dataset;
                INTERSECTED_SECTION.set(section);
            }
        }
        const observer = new IntersectionObserver(handler, options);

        observer.observe(document.querySelector('.skills'));   
        observer.observe(document.querySelector('.projects'));   
    })
</script>

<main class="feed">
  <section 
    class="projects hover:blur"
    data-section="projects"
    >
    {#each Array.from({ length: 10 }) as item, index}
      <div
        class="project hover:scale">
        Lorem ipsum dolor sit amet.
      </div>
    {/each}
  </section>

  <section 
    class="skills hover:blur"
    data-section="skills"
    >
    {#each Array.from({ length: 10 }) as item}
      <div class="skill hover:scale">Lorem ipsum dolor sit amet.</div>
    {/each}
  </section>
</main>

<style>
    .feed {
        grid-column-start: 2;
    }

    .projects {
        margin-bottom:10rem;
    }

    .hover\:scale, .hover\:blur {
        transition: 0.4s transform cubic-bezier(0.175, 0.885, 0.32, 1.275), 0.25s opacity cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }

    .hover\:blur:hover > * {
        opacity:0.3;
    }

    .hover\:blur:hover .hover\:scale:hover {
        opacity: 1;
    }

    .project {
        position: relative;

        z-index: 3;

        padding: 3rem 0.5rem;
        margin-bottom: 0.5rem;

        border-radius: 5px;

        box-shadow: 5px 5px 21px 9px rgba(0, 0, 0, 0.34);

        background-color: #181818;
    }

    .hover\:scale:hover,
    .hover\:scale.active {
        z-index: 100;
        transform: scale(1.2);
    }

    .skills {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-auto-rows: 65px;
        grid-auto-flow: row;
        gap: 0.5rem;
    }

    .skill {
        grid-row: span 4;
        
        border-radius: 5px;

        box-shadow: 5px 5px 21px 9px rgba(0, 0, 0, 0.34);

        background-color: #181818;
    }

    .skill:nth-child(2) {
        grid-row: 2 / span 4;
        grid-column-start: 2;
    }

    @media screen and (max-width: 900px) {
        .feed {
            grid-column-start: auto;
        } 
    }
</style>