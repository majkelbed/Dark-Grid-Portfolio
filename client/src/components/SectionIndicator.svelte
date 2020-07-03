<script>
    import { INTERSECTED_SECTION } from '../stores/HomePage.js';

    const sections = ['projects', 'skills'];
    let activeSection = 'projects';

    INTERSECTED_SECTION.subscribe(section => activeSection = section);
</script>

{#each sections as section, index}
    <span class="section" class:active={section == activeSection}>
        0{index+1} <div class="line-separator"></div> {section}
    </span>
{/each}

<style>
    .section {
        display: flex;
        align-items: center;
        margin:1rem 0;
        transition: 0.3s transform cubic-bezier(0.175, 0.885, 0.32, 1.275);
        transform-origin: left center;
    }

    .section.active {
        font-weight: bold;
        transform: scale(1.1);
    }

    .line-separator {
        height: 2px;
        width: 3rem;
        margin: 0 1rem;
        background:white;
    }
</style>