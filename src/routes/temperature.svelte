<script>
	import Axis from '../components/Axis.svelte';
	import Percentage from '../components/Percentage.svelte';

	const colonyWideData = {
		labels: ["2020/06/20 10:30", "2020/06/20 10:31", "2020/06/20 10:32", "2020/06/20 10:33",
			"2020/06/20 10:34", "2020/06/20 10:35", "2020/06/20 10:36", "2020/06/20 10:37"
		],
		yRegions: [
    {
			label: "Acceptable Range",
			start: 30,
			end: 10,
			options: { labelPos: 'right' }
    }
		],
		datasets: [
			{
				name: "Temperature", chartType: "line",
				values: [25, 50, -10, 15, 18, 32, 27, 14]
			},
			{
				name: "Expected Temperature", chartType: "line",
				values: [22, 30, -15, 17, 19, 30, 27, 15]
			}
		]
	}

	const colonyStatus = {
		labels: ["Underheating", "Nominal", "Overheating"],
		datasets: [
			{
				values: [4, 4, 8]
			},
		]
	}
	const statusColors = ['blue', 'green', 'red'];
</script>

<style>
	.grid {
		display: grid;
		grid-template-columns: 25% 25% 25% 25%;
	}
</style>

<svelte:head>
	<title>HabNet - Temperature</title>
</svelte:head>

<h2>Colony-wide (16 habitats)</h2>
<div>
	<Axis id="colony-mean" chartTitle="Mean, in celsius" data={colonyWideData} />
	<Percentage id="colony-status" chartTitle="Status" data={colonyStatus} colors={statusColors} />
</div>
<h2>Overheating (8/16)</h2>
<div class="grid">
	<Axis id="habitat-1" chartTitle='Habitat #1' data={colonyWideData} />
	<Axis id="habitat-4" chartTitle='Habitat #4' data={colonyWideData} />
	<Axis id="habitat-6" chartTitle='Habitat #6' data={colonyWideData} />
	<Axis id="habitat-5" chartTitle='Habitat #5' data={colonyWideData} />
	<Axis id="habitat-15" chartTitle='Habitat #15' data={colonyWideData} />
	<Axis id="habitat-44" chartTitle='Habitat #44' data={colonyWideData} />
	<Axis id="habitat-64" chartTitle='Habitat #64' data={colonyWideData} />
	<Axis id="habitat-54" chartTitle='Habitat #54' data={colonyWideData} />
</div>

<h2>Underheating (4/16)</h2>
<div class="grid">
	<Axis id="habitat-8" chartTitle='Habitat #8' data={colonyWideData} />
	<Axis id="habitat-9" chartTitle='Habitat #9' data={colonyWideData} />
	<Axis id="habitat-10" chartTitle='Habitat #10' data={colonyWideData} />
	<Axis id="habitat-11" chartTitle='Habitat #11' data={colonyWideData} />
</div>

<h2>Nominal (4/16)</h2>
<div class="grid">
	<Axis id="habitat-48" chartTitle='Habitat #48' data={colonyWideData} />
	<Axis id="habitat-29" chartTitle='Habitat #29' data={colonyWideData} />
	<Axis id="habitat-510" chartTitle='Habitat #510' data={colonyWideData} />
	<Axis id="habitat-611" chartTitle='Habitat #611' data={colonyWideData} />
</div>
