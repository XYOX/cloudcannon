<script>
    import * as nav from '@data/nav.json';
    import { page } from '$app/stores';

    const currentPath = $page.url.pathname;
</script>

<header>
    <nav
        class="navbar navbar-expand-lg position-fixed w-100 zindex-dropdown"
        id="mainnavigationBar"
    >
        <div class="container-fluid">
            <a class="navbar-brand" target="_self" href="/">
                <img src={nav.logo} alt="Nav-Logo" />
            </a>
            <button
                class="navbar-toggler"
                type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <span class="navbar-toggler-default">
                    <svg
                        width="24"
                        height="24"
                        viewBox="0 0 24 24"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <line
                            x1="3.5"
                            y1="5.5"
                            x2="21.5"
                            y2="5.5"
                            stroke="#292D32"
                            stroke-width="3"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        />
                        <line
                            x1="4.5"
                            y1="12.5"
                            x2="21.5"
                            y2="12.5"
                            stroke="#292D32"
                            stroke-width="3"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        />
                        <line
                            x1="11.5"
                            y1="19.5"
                            x2="21.5"
                            y2="19.5"
                            stroke="#292D32"
                            stroke-width="3"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        />
                    </svg>
                </span>
                <span class="navbar-toggler-toggled">
                    <svg
                        width="20"
                        height="20"
                        viewBox="0 0 28 28"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <path
                            d="M21.5 6.5L6.5 21.5"
                            stroke="#404152"
                            stroke-width="3"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        />
                        <path
                            d="M21.5 21.5L6.5 6.5"
                            stroke="#404152"
                            stroke-width="3"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        />
                    </svg>
                </span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav mx-auto mb-20 mb-lg-0">
                    {#each nav.items as item}
                        <li class="nav-item">
                            <a
                                class="nav-link"
                                class:active={currentPath === item.link}
                                href={item.link}
                                target="_self">{item.text}</a
                            >
                        </li>
                    {/each}
                </ul>
            </div>
            <div class="d-none d-lg-block">
                <div class="nav-item">
                    <a href={nav.button.link} class="btn btn-sm btn-links"
                        >{nav.button.text}</a
                    >
                </div>
            </div>
        </div>
    </nav>
</header>
