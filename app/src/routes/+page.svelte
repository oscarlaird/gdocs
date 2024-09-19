<script>
    import { precalc_concepts, stat_concepts } from "./concepts";
    import "./app.css";
    import PrinterPage from "./PrinterPage.svelte";
    import ConceptChecklist from "./ConceptChecklist.svelte";
    import PhysicsConcepts from "./PhysicsConcepts.svelte";
    let title="Physics Concepts Progress";
    let instructions="Fill in the circle that corresponds to your highest grade on each concept.";
    let n_levels = 5;
    let concepts_text = precalc_concepts;
    let start_idx = 0;
    let max_concepts = 14;
    $: all_concepts = concepts_text.split('\n').filter(c => c.length > 0);
    $: concepts = all_concepts.slice(start_idx, start_idx + max_concepts);
</script>

<PrinterPage>
    <PhysicsConcepts concepts={concepts} title={title} instructions={instructions} n_levels={n_levels} />
</PrinterPage>

<hr>
Title:  <input type="text" bind:value={title} />
<br>
Instructions:  <input type="text" bind:value={instructions} />
<br>
Concepts per sheet  <input type="number" bind:value={max_concepts} min="3" max="30" step="1" />
<br> 
Start index  <input type="number" bind:value={start_idx} min="0" max={all_concepts.length - max_concepts} step="1" />
<br>
<hr>
Concepts (one per line) <br>
Choose from presets:
<select bind:value={concepts_text}>
    <option value={precalc_concepts}>Precalculus</option>
    <option value={stat_concepts}>Statistics</option>
</select>
<br>
<textarea bind:value={concepts_text} rows="35" cols="100"></textarea>


<style>
    input{
        width: 600px;
    }
    input[type="number"]{
        width: 50px;
    }
</style>