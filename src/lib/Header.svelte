<script>
    import { page } from "$app/stores";
    let isMenuOpen = false;

    const toggleMenu = () => {
        isMenuOpen = !isMenuOpen;
    };
</script>

<header>
    <div class="corner">
        <a href="https://teamdhruva.com/">
            <img
                src="https://teamdhruva.com/text_logo.webp"
                alt="Dhruva logo"
            />
        </a>
    </div>

    <button
        class="hamburger"
        aria-label="Toggle navigation"
        on:click={toggleMenu}
    >
        <span></span>
        <span></span>
        <span></span>
    </button>

    <nav class={isMenuOpen ? "open" : ""}>
        <ul>
            <li aria-current={$page.url.pathname === "/" ? "page" : undefined}>
                <a href="/">Home</a>
            </li>
            <li
                aria-current={$page.url.pathname === "/blogs"
                    ? "page"
                    : undefined}
            >
                <a href="/blogs">Blogs</a>
            </li>
            <li
                aria-current={$page.url.pathname.startsWith(
                    "/indian-astrophysics",
                )
                    ? "page"
                    : undefined}
            >
                <a href="/indian-astrophysics">Indian Astrophysics</a>
            </li>
            <li
                aria-current={$page.url.pathname.startsWith("/journal")
                    ? "page"
                    : undefined}
            >
                <a href="/journal">Journal</a>
            </li>
            <li
                aria-current={$page.url.pathname === "/about"
                    ? "page"
                    : undefined}
            >
                <a href="/about">About</a>
            </li>
            <li
                aria-current={$page.url.pathname.startsWith("/team")
                    ? "page"
                    : undefined}
            >
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
        border-bottom: 2px solid white; 
        backdrop-filter: blur(500px);
    }

    .corner img {
        width: 35%;
        height: auto;
        margin-left: 20px;
    }

    .hamburger {
        display: none;
        flex-direction: column;
        justify-content: space-around;
        width: 30px;
        height: 25px;
        background: none;
        border: none;
        cursor: pointer;
    }

    .hamburger span {
        width: 20px;
        height: 3px;
        background-color: white;
        border-radius: 2px;
    }

    nav {
        display: flex;
        align-items: center;
    }

    nav ul {
        padding: 0;
        margin: 0;
        display: flex;
        list-style: none;
        gap: 25px;
        font-size: larger;
        font-weight: bold;
    }

    nav ul li {
        margin-right: 20px;
    }

    nav ul li a {
        color: white;
        text-decoration: none;
    }

    nav ul li[aria-current="page"] a {
        font-weight: bold;
        color: aqua;
    }

    nav ul li a:hover {
        color: #0d92f4;
    }

    /* Mobile Styles */
    @media (max-width: 768px) {
        .hamburger {
            display: flex;
        }

        nav {
            position: absolute;
            top: 60px;
            left: 0;
            right: 0;
            background-color: rgba(0, 0, 0, 0.9);
            /* border-left: 2px solid white; */
            width: 100%;
            padding: 30px;
            flex-direction: column;
            align-items: flex-start;
            display: none;
            text-align: center;
        }

        nav.open {
            display: flex;
            width: 80%;
        }

        nav ul {
            flex-direction: column;
            gap: 10px;
            width: 100%;
        }

        nav ul li {
            margin: 0;
            /* width: 100%; */
            text-align: center;
        }

        nav ul li a {
            display: block;
            width: 100%;
            padding: 10px 0;
        }
    }
</style>
