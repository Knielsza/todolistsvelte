<script>
	export let title;
	export let index;
	export let onEdit;

	export let onRemove = (i) => {console.log("AA")};
	let editedTitle = title
	let isEditing 

	const confirmEdit = () => {
		if(editedTitle != ""){
				onEdit(index, editedTitle);
				isEditing = false;
			}
	}
	const cancelEdit = () => {
		isEditing = false;
		editedTitle = title
	}
</script>

<div class="wrapper">
{#if !isEditing}
	<p>{title}</p>
		<div class="button-container">
			<button on:click={() => {isEditing = true}}>Edit</button>
			<button on:click={() => {onRemove(index)}}>Remove</button>
		 </div>
{:else}
		 <input type="text" placeholder="Title..." bind:value={editedTitle}>
		 <div class="button-container">
			 <button class="green-gerni" on:click={() => {
				confirmEdit()
			}
			}>save</button >
			 <button on:click={() => {
				cancelEdit()
				}}>Cancel</button>
		  </div>

{/if}
</div>
<style >
	.green-gerni{
		background-color: fuchsia;


	}
	div {
		height: 2rem;
		background-color: lightblue;
		border-bottom: 3px solid lightcoral;
		display: flex;
		justify-content: space-between;
	}

	button {
		margin-top: 5px;
		margin-bottom: 5px;
		border-radius: 5px;
		margin-left: auto;
		max-width: 250px;
		background-color: lightcoral;
		border: 0;
		height: 80%;
		width: 10vw;
	}
</style>