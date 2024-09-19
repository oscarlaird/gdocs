<script>

</script>

<div class="container">
    <slot></slot>
</div>

<style>
    .container{
        height: calc(8.5 * 96px);
        width: calc(11 * 96px);
        background: white;
        outline: 4px solid black;
    }
    @media print{
        .container{
            position: absolute;
            width: 100%;
            height: 100%;
            left: 0;
            top: 0;
            outline: 1px solid red;
        }
    }
</style>