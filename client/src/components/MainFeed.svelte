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
    class="projects"
    data-section="projects"
    >
    {#each Array.from({ length: 10 }) as item, index}
      <div
        class="project">
        Lorem ipsum dolor sit amet.
      </div>
    {/each}
  </section>
  <section 
    class="skills"
    data-section="skills"
    >
    {#each Array.from({ length: 10 }) as item}
      <div class="skill">Lorem ipsum dolor sit amet.</div>
    {/each}
  </section>
</main>

<style>
    .feed {
        grid-column-start: 2;
    }

    .projects:hover .project {
        opacity:0.3;
    }

    .projects:hover .project:hover {
        opacity: 1;
    }

    .project {
        position: relative;

        z-index: 3;

        padding: 3rem 0.5rem;
        margin-bottom: 0.5rem;

        border: 2px solid white;
        border-radius: 5px;

        box-shadow: 5px 5px 21px 9px rgba(0, 0, 0, 0.34);

        background-color: #151515;

        transition: 0.25s transform ease-in-out, 0.25s opacity ease-in-out;
    }

    /* .project::after {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        z-index: 50;
        background-color: #151515;
        opacity: 0;
        transition: 0.2s opacity ease-in-out;
    } */

    .project:hover,
    .project.active {
        z-index: 100;
        transform: scale(1.2);
    }

    /* .project.dimmed::after {
        opacity: 0.4;
    } */

    .skills {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-auto-rows: 65px;
        grid-auto-flow: row;
        gap: 0.5rem;
    }

    .skill {
        border: 2px solid white;
        border-radius: 5px;
        grid-row: span 4;
    }

    .skill:nth-child(2) {
        grid-row: 2 / span 4;
        grid-column-start: 2;
    }
</style>