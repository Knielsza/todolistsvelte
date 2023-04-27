<script>
	import Item from '@/lib/Item.svelte';
 	export let onEdit;
	export let items = [];
	export let onRemove = (i) => {console.log("AAA")};
</script>

<div>
	{#each items as item, index}
		<Item title={item} index={index} onRemove={onRemove} onEdit={onEdit}/>
	{/each}
</div>

<style>
	div {
		border-top: 3px solid lightcoral;
	}
</style>