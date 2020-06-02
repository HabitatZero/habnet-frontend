<script>
  import { onMount } from 'svelte';
  import { Chart } from "frappe-charts/dist/frappe-charts.min.esm"

  export let id;
  export let chartTitle;
  export let data;
  export let colors = ['#743ee2', '#7cd6fd'];

  onMount(async () => {
   const chart = await new Chart(`#${id}`, {
      title: chartTitle,
      data: data,
      type: 'percentage',
      colors: colors,
    })
  });
</script>

<div id="{id}" class="percentage"></div>
