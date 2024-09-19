<script>
    export let concept = '';
    export let is_scale = false;
    export let n_levels = 5;

</script>

<div class="container"
  class:is_scale={is_scale}
>
    <div class="dotted_line"></div>
    <div class="circles"
    >
        {#each Array(n_levels + 1) as _, i}
            <div class="circle"
                style:width={i===0 ? 0 : 30 + 6*(i-1) + 'px'}
            >
                {is_scale ? (i===0 ? '' : i) : ''}
            </div>
        {/each}
    </div>
    <div class="label_outer">
        <div class="label_inner">
            {concept}
        </div>
    </div>
</div>

<style>
    .container {
        position: relative;
        height: 100%;
    }
    .circles {
        height: 100%;
        position: relative;
        display: flex;
        flex-direction: column-reverse;
        justify-content: space-between;
        align-items: center;
    }
    .circle {
        aspect-ratio: 1/1;
        border-radius: 50%;
        border: 2px solid black;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: white;
        z-index: 2;
        background: radial-gradient(circle);
    }
    .dotted_line {
        position: absolute;
        left: calc(50% - 2px);
        height: 100%;
        border-left: 3px dotted black;
        z-index: 1;
    }
    .container.is_scale .circle {
        border: none;
        background-color: transparent;
        font-size: x-large;
        font-weight: bold;
    }
    .container.is_scale .dotted_line {
        display: none;
    }
    .circles .circle:first-of-type {
        visibility: hidden;
    }
    .label_outer {
        height: 3rem;
        width: 10rem;
        position: absolute;
        right: 50%;
        bottom: 0;
        border-bottom: 2px solid black;
        transform-origin: 100% 100%;
        transform: rotate(-70deg);
        display: flex;
        justify-content: center;
        align-items: flex-end;
    }
    .label_inner {
        font-size: 0.9rem;
        margin-right: 20px;
        text-align: center;
    }
    .container.is_scale .label_outer {
        display: none;
    }
</style>