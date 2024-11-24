<script lang="ts">
    import Icon from '@iconify/svelte'
    import Projects from '$lib/projects'
</script>

<svelte:head>
    <title>FuryForever - Projects.</title>
</svelte:head>

<section class="main">
    <div class="content screen">
        <h1>Projects.</h1>
        <ul>
            {#each Projects as project, index}
                <li>
                    <a href={project.ProjectURL}>
                        <h3>{index + 1}. {project.Title}</h3>
                    </a>
                    <div>
                        <p>{project.Description}</p>
                        <p class="technologies">Technologies: {project.Tags}</p>
                    </div>
                    <a href={project.RepositoryURL}>
                        <Icon icon="mdi:github" width="2rem" height="2rem" /> Github repository
                    </a>
                </li>
            {/each}
        </ul>
    </div>
    <div class="divider screen"></div>
    <nav class="navbar">
        <ul>
            <li>
                <a href="/">Home</a>
            </li>
            <li>
                <a href="/projects">Projects</a>
            </li>
            <li>
                <a href="/blog">Blog</a>
            </li>
            <li>
                <a href="mailto:furyforeverdev@gmail.com">Contact</a>
            </li>
        </ul>
    </nav>
    <nav class="socials">
        <ul>
            <li>
                <a href="https://github.com/Furyforev3r/">
                    <Icon icon="mdi:github" width="2rem" height="2rem" />
                </a>
            </li>
            <li>
                <a href="https://x.com/FuryForev3r/">
                    <Icon icon="mdi:twitter" width="2rem" height="2rem" />
                </a>
            </li>
            <li>
                <a href="https://www.linkedin.com/in/messias-dev/">
                    <Icon icon="mdi:linkedin" width="2rem" height="2rem" />
                </a>
            </li>
        </ul>
    </nav>
</section>

<style>
    .main {
        display: flex;
        flex-direction: column;
        gap: 0.8rem;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100%;
    }

    .screen {
        width: 50%;
    }

    .content ul {
        margin-top: 0.3rem;
        padding-right: 0.3rem;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        height: 300px;
        overflow-y: auto;
        gap: 1rem;
    }

    .content ul::-webkit-scrollbar {
        width: 10px;
        background: var(--sideBar-background);
    }

    .content ul::-webkit-scrollbar-thumb {
        background: var(--scrollbar-shadow);
        border-radius: 0.8rem;
    }

    .content ul li {
        cursor: pointer;
        display: flex;
        flex-direction: column;
        gap: 0.3rem;
        padding: 1rem;
        border: solid 0.1rem var(--focusBorder);
        border-radius: 0.3rem;
        width: 100%;
        transition: background 0.3s;
    }

    .content ul li:hover {
        background: var(--button-background);
    }

    .content ul li a {
        color: var(--text-color);
        text-decoration: underline;
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 0.3rem;
    }

    .divider {
        height: 1px;
        background: var(--focusBorder);
        border-radius: 0.3rem;
    }

    .navbar ul {
        display: flex;
        flex-direction: row;
        gap: 0.3rem;
    }

    .navbar ul li a {
        display: block;
        text-align: center;
        color: var(--text-color);
        text-decoration: none;
        background: var(--button-background);
        padding: 0.8rem;
        border-radius: 0.3rem;
        transition: background 0.3s;
    }

    .navbar ul li a:hover {
        background: var(--button-hover);
    }

    .socials ul {
        display: flex;
        flex-direction: row;
        gap: 0.3rem;
    }

    .socials ul li a :global(svg) {
        color: var(--text-color);
        transition: color 0.3s;
    }

    .socials ul li a :global(svg):hover {
        color: var(--text-alternative);
    }

    .technologies {
        color: var(--title-color);
        transition: color 0.3s;
    }

    .technologies:hover {
        color: var(--text-alternative);
        text-decoration: underline;
    }
</style>