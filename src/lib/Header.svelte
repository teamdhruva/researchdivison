<!-- src/lib/Header.svelte -->
<script>
    import { page } from '$app/stores';
</script>

<header>
    <div class="corner">
        <a href="https://teamdhruva.com/">
            <img src="https://teamdhruva.com/text_logo.webp" alt="Dhruva logo">
        </a>
    </div>

    <nav>
        <ul>
            <li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
                <a href="/">Home</a>
            </li>
            <li aria-current={$page.url.pathname === '/blogs' ? 'page' : undefined}>
                <a href="/blogs">Blogs</a>
            </li>
            <li aria-current={$page.url.pathname.startsWith('/indian-astrophysics') ? 'page' : undefined}>
                <a href="/indian-astrophysics">Indian Astrophysics</a>
            </li>
            <li aria-current={$page.url.pathname.startsWith('/journal') ? 'page' : undefined}>
                <a href="/journal">Journal</a>
            </li>
            <li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
                <a href="/about">About</a>
            </li>
            <li aria-current={$page.url.pathname.startsWith('/team') ? 'page' : undefined}>
                <a href="/team">Team</a>
            </li>
        </ul>
    </nav>
</header>

<style>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 10px;
        background-color: transparent;
        color: white;
        border-bottom: 2px solid white; /* White line under the header */
    }

    .corner img {
        width: 35%; /* Adjust as needed (e.g., '50%', '200px', etc.) */
        height: auto; /* Maintain aspect ratio */
        margin-left: 20px;
    }

    nav ul {
        padding: 0;
        margin: 0;
        height: 3em;
        display: flex;
        justify-content: center;
        align-items: center;
        list-style: none;
        background: var(--background);
        background-size: contain;
        gap: 25px;
        font-size: larger;
        margin-right: 15px;
        font-weight: bold;
    }

    nav ul li {
        margin-right: 20px;
    }

    nav ul li a {
        color: white;
        text-decoration: none;
    }

    nav ul li[aria-current='page'] a {
        font-weight: bold;
        color: aqua;
    }

    nav ul li a:hover {
        color:#0D92F4;
    }
</style>
