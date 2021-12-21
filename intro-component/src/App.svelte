<script lang="ts">
    import Header from "./components/Header.svelte";
    import Form from "./components/Form.svelte";
    let innerWidth = 0;
    $: isMobile = innerWidth <= 1440;
    $: document.body.id = isMobile ? "mobile-body" : "desktop-body";
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
        href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap"
        rel="stylesheet"
    />
    <link
        rel="shortcut icon"
        href="/assets/favicon-32x32.png"
        type="image/x-icon"
    />
</svelte:head>
<svelte:window bind:innerWidth />
<div id="app">
    <div id="wrapper">
        <Header />
        <Form />
    </div>
</div>

<style>
    #app {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
    }
    #wrapper {
        display: flex;
        align-items: center;
        width: 1200px;
    }
    @media all and (max-width: 1440px) {
        #app {
            display: block;
            padding: 100px 0;
            height: auto;
        }
        #wrapper {
            flex-direction: column;
            width: 90%;
            margin: 0 auto;
        }
    }
</style>
