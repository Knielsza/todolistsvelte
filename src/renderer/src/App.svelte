<script>
	import TodoList from '@/lib/TodoList.svelte';
	import ItemInput from '@/lib/ItemInput.svelte';

	let items = ["First task", "Second task", "Third task"];

	function addItem(item) {
		items = [...items, item];
	}
	function editItem(index, value) {
		// items = items.map((el, i) => {
		// 	if()
		// })
		items[index] = value;
	}
	function removeItem(index) {
		items = items.filter((_, i) => i !== index);
	}
</script>

<main>
	<ItemInput onAdd={addItem} />
	<TodoList {items} onRemove={removeItem} onEdit={editItem} />

</main>

<style>
	main {
		background-color: lightblue;
		margin: 0;
		padding: 15px;
		min-height: calc(100vh - 30px);
	}
	:global(body) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
</style>
