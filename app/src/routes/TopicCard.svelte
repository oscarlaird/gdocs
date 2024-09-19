<script>
    export let topic;
</script>

<div class="container">
    <div class="topic_text">
        {topic}
    </div>
    <div class="checkballs">
        {#each Array(5) as _, i}
            <div class="checkball">
                {i+1}
            </div>
        {/each}
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        width: 150px;
        height: 100px;
        border: 2px solid black;
        border-radius: 6px;
    }
    .topic_text {
        width: 100%;
        display: flex;
        flex: 2;
        justify-content: center;
        align-items: center;
        text-align: center;
    }
    .checkballs {
        display: flex;
        flex: 1;
        flex-direction: row;
        justify-content: space-around;
    }
    .checkball {
        height: 15px;
        aspect-ratio: 1/1;
        border: 2px solid black;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: small;
    }
</style>