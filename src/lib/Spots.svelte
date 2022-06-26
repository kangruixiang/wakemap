<script>
	import Typeahead from 'svelte-typeahead';
	import data from './locations';

	let events = '';
</script>

<Typeahead
	label=""
	placeholder={`Search Wake Locations`}
	{data}
	extract={(item) => item.abbr}
	on:select={({ detail }) => (events = detail['original']['state'])}
	on:clear={() => (events = '')}
	let:result
	let:index
>
	<div>
		{@html result.string}
	</div>
</Typeahead>

<div class="font-serif mx-12 my-8 text-xl flex items-center justify-center">{@html events}</div>

<style>
	:global([role='listbox']) {
		margin: 0;
	}
</style>
