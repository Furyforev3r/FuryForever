<script lang="ts">
	import Icon from '@iconify/svelte'

	let currentDate = new Date()
	let dateOfBirth = new Date(2008, 11, 14)

	let ageInMs = currentDate.getTime() - dateOfBirth.getTime()
	let millisecondsInYear = 1000 * 60 * 60 * 24 * 365.25

	let age = Math.floor(ageInMs / millisecondsInYear)
</script>

<svelte:head>
	<title>FuryForever.</title>
	<meta name="description" content="My portfolio website." />
	<meta name="keywords" content="projects, software development, programming, FuryForever" />
</svelte:head>

<section class="main">
	<div class="content">
		<h1>FuryForever.</h1>
		<p>Hi there! I'm <span>Messias</span> aka FuryForever (or Rob). I'm <span>{age} y/o</span> and I'm a <span>Software Engineer!</span></p>
		<p>I like developing useful things and turning ideas into reality.</p>
	</div>
	<div class="divider"></div>
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

	.main div {
		width: 50%;
	}

	.main span {
		cursor: pointer;
		color: var(--text-alternative);
	}

	.main span:hover {
		text-decoration: underline;
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
</style>