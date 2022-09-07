<script>
	import User from "./user/User.svelte"
    import Logo from "./components/Logo.svelte"
    import Icon from 'svelte-icon'
    import Home from "./home/Home.svelte"
    import Org from "./org/Org.svelte"
    import home from './components/Icon/icon-home.svg'
    import student from './components/Icon/icon-students.svg'
    import graph from './components/Icon/icon-graph.svg'

    export let activeContent = 'home'

</script>

<div class="grid-container">
    <div class="header">Header</div>
    <div class="sidebar">
        <div id="logoContainer">
            <Logo />
        </div>
        <div class="brand-name macMan">
            Udugelighets - modul
        </div>
        <div class="sidenav-list-wrapper">
            <ul class="sidenav-list">
                <li class="sidenav-item">
                    <button on:click={() => activeContent = 'home'}>Hjem</button>
                    <Icon data={home} height="30px" width="30px" class="hoverable" />
                </li>
                <li class="sidenav-item">
                    <button on:click={() => activeContent = 'user'}>Meg</button>
                    <Icon data={student} height="30px" width="30px" class="hoverable" />
                </li>
                <li class="sidenav-item">
                    <button on:click={() => activeContent = 'org'}>Organisasjon</button>
                    <Icon data={graph} height="30px" width="30px" class="hoverable" />
                </li>
            </ul>
        </div>
    </div>
    <div class="main">
        { #if activeContent === 'home'}
            <Home />
        { :else if activeContent === 'user' }
            <User />
        { :else if activeContent === 'org' }
            <Org />
        {/if }
    </div>
</div>

<style>
    .header {
        grid-area: header;
        /* max-height: 20px; */
    }
    .sidebar {
        grid-area: sidebar;
        background-color: var(--potPourri);
        /* min-width: 200px;
        max-width: 250px; */
        text-align: center;
    }
    .main {
        grid-area: main;
    }

    .grid-container {
        display: grid;
        grid-template-areas:
            'sidebar header'
            'sidebar main';
        grid-template-rows: 20px auto;
        grid-template-columns: 200px auto;
        gap: 0px;
        padding: 0px;
        min-height: 100%;
    }

    .grid-container > div {
        padding: 0px 0;
        font-size: 30px;
    }
    .brand-name {
        font-size: 24px;
        font-weight: 700;
        line-height: 1.5;
    }
    .sidenav-list-wrapper {
        margin-top: 100px;
    }
    #logoContainer {
        width: 45px;
        margin: auto;
        margin-top: 32px;
    }
    .sidenav-list {
        list-style: none;
        margin: 0;
        padding: 0;
        text-align: center;
        width: 100%;
    }
    .sidenav-item {
        display: block;
    }
</style>