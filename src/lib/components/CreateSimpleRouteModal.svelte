<script>
	import { goto } from '$app/navigation';

	/**
	 * @type {() => any}
	 */
	export let close;
	let startLocation = '';
	let endLocation = '';
	// Add other necessary logic and props here
	async function handleSubmit() {
		// You can handle the form submission logic here
		// For now, just log the input values
		console.log('Start Location:', startLocation);
		console.log('End Location:', endLocation);

		// Close the modal
		await close();

		// Introduce a 200ms delay using setTimeout
		await new Promise((resolve) => setTimeout(resolve, 50));

		// After the delay, navigate to '/ruta-simple'
		await goto('/ruta-simple');
	}
</script>

<div class="modal-overlay">
	<div class="modal">
		<!-- Modal content goes here -->
		<div class="modal-content">
			<h2 class="text-lg font-semibold mb-4">Formulario de Ruta</h2>

			<!-- Start Location input -->
			<div class="mb-4">
				<label for="startLocation" class="block text-sm font-medium text-gray-700"
					>Ubicacion de Inicio:</label
				>
				<input
					type="text"
					bind:value={startLocation}
					id="startLocation"
					name="startLocation"
					class="mt-1 p-2 border rounded-md w-full"
					placeholder="Enter start location"
				/>
			</div>

			<!-- End Location input -->
			<div class="mb-4">
				<label for="endLocation" class="block text-sm font-medium text-gray-700"
					>Ubicacion Final:</label
				>
				<input
					type="text"
					bind:value={endLocation}
					id="endLocation"
					name="endLocation"
					class="mt-1 p-2 border rounded-md w-full"
					placeholder="Enter end location"
				/>
			</div>

			<!-- Submit button -->
			<button
				on:click={handleSubmit}
				class="bg-blue-500 text-white p-2 rounded-md hover:bg-blue-600">Submit</button
			>

			<!-- Close button -->
			<button
				on:click={close}
				class="ml-2 bg-gray-300 text-gray-700 p-2 rounded-md hover:bg-gray-400">Close</button
			>
		</div>
	</div>
</div>

<style>
	/* Add your modal styling here */
	.modal-overlay {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0, 0, 0, 0.5);
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.modal {
		background: white;
		padding: 20px;
		border-radius: 8px;
		box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
	}

	/* Add more styling as needed */
</style>
