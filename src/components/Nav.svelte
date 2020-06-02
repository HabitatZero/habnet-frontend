<script>
	export let segment;
</script>

<style>
	nav {
		border-bottom: 1px solid rgba(255,62,0,0.1);
		font-weight: 300;
		padding: 0 1em;
	}

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	[aria-current] {
		position: relative;
		display: inline-block;
	}

	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: rgb(255,62,0);
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 1em 0.5em;
		display: block;
	}
</style>

<nav>
	<ul>
		<li><a class="mono" aria-current="{segment === undefined ? 'page' : undefined}" href=".">Overview</a></li>
		<li><a class="mono" aria-current="{segment === 'map' ? 'page' : undefined}" href="map">Map</a></li>
		<li><a class="mono" aria-current="{segment === 'habitats' ? 'page' : undefined}" href="habitats">Habitats</a></li>
		<li><a class="mono" aria-current="{segment === 'air' ? 'page' : undefined}" href="air">Air</a></li>
		<li><a class="mono" aria-current="{segment === 'water' ? 'page' : undefined}" href="water">Water</a></li>
		<li><a class="mono" aria-current="{segment === 'energy' ? 'page' : undefined}" href="energy">Energy</a></li>
		<li><a class="mono" aria-current="{segment === 'temperature' ? 'page' : undefined}" href="temperature">Temperature</a></li>
		<li><a class="mono" aria-current="{segment === 'humidity' ? 'page' : undefined}" href="humidity">Humidity</a></li>
		<li><a class="mono" aria-current="{segment === 'lighting' ? 'page' : undefined}" href="lighting">Lighting</a></li>
		<li><a class="mono" aria-current="{segment === 'noise' ? 'page' : undefined}" href="noise">Noise</a></li>
		<li><a class="mono" aria-current="{segment === 'alerts' ? 'page' : undefined}" href="alerts">Alerts</a></li>
	</ul>
</nav>
