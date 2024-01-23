<script lang="ts">
	import type { APISchema } from '$lib/docs/types.js';
	import { APITable, APIWrapper } from '$lib/docs/components/index.js';

	export let schemas: APISchema[];
</script>

<APIWrapper>
	{#each schemas as schema}
		<APITable data={schema} />
	{/each}
</APIWrapper>
