<script>
    let units = [];
    import TopicCard from "./TopicCard.svelte";
</script>

<div class="container">
    {#each units as unit, i}
        <div class="unit">
            <div class="unit_name">
                {i+1}. {unit.name}
            </div>
            <div class="topic_cards">
            {#each unit.topics as topic}
                <TopicCard topic={topic} />
            {/each}
            </div>
        </div>
    {/each}
</div>

<style>
    .container {
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
    }
    .topic_cards {
        display: flex;
        flex-flow: row nowrap;
        justify-content: center;
        gap: 20px;
    }
    .unit_name {
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: large;
        font-weight: bold;
    }

</style>