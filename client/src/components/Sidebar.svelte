<script>
    import SectionIndicator from './SectionIndicator.svelte';
</script>

<aside class="sidebar">
    <h1 class="sidebar_title">
        Hello, I'm <br>
        Michał Bednarczyk
    </h1>

    <p class="sidebar_bio">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. 
        Eius, nesciunt harum consequatur facilis odit velit cum vitae temporibus 
        laudantium inventore eaque suscipit similique sequi fugiat est, 
        corrupti ullam, modi cumque?
        nesciunt harum consequatur facilis odit velit cum vitae temporibus 
        laudantium inventore eaque suscipit similique sequi fugiat.
    </p>

    <SectionIndicator></SectionIndicator>

    <div class="sidebar_social-media">
        <a class="link" href="">Twitter</a>
        <a class="link" href="">Github</a>
    </div>
</aside>

<style>
    .sidebar {
        position: fixed;
        display: flex;
        flex-direction: column;

        z-index: 0;
        width: calc(50% - 3rem);
        min-width: 300px;
        max-width: 630px;
        height: 100%;

        padding-right:2rem;
    }

    .sidebar_title {
        margin-bottom: 1.5rem;

        font-size: 4rem;
        line-height: 1.2;
    }

    .sidebar_bio {
        font-size:1rem;
        line-height: 2;
    }

    .sidebar_social-media {
        margin-top:auto;
    }

    @media screen and (max-width: 900px) {
		.sidebar {
			position: relative;
            width: 100%;
            max-width: 100%;
		}
	}

</style>