<script>
    import Concept from "./Concept.svelte";
    export let title;
    export let instructions;
    export let n_levels;
    export let concepts;
</script>

<div class="container">
    <div class="header">
        <div class="title">
            {title}
        </div>
        <div class="instructions">
            {instructions}
        </div>
    </div>
    <div class="concepts">
        <Concept is_scale={true} n_levels={n_levels} />
        {#each concepts as concept}
            <Concept concept={concept} n_levels={n_levels} />
        {/each}
    </div>
    <div class="header" />
</div>

<style>
    .container {
        height: 100%;
        display: flex;
        flex-direction: column;
    }
    .header {
        flex: 1;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .header .title {
        font-size: 1.8em;
        font-weight: bold;
    }
    .header .instructions {
        margin-top: 20px;
        font-style: italic;
    }
    .concepts {
        flex: 3;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
        border-bottom: 4px solid black;
        padding-right: 15px;
    }
</style>
