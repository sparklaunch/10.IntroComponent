<script lang="ts">
    import Header from "./components/Header.svelte";
    import Form from "./components/Form.svelte";
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
</style>
