<script lang="ts">
	import { scaleThreshold } from "d3-scale";
	import { timeYear } from "d3-time";
	import { Chart, Calendar, Tooltip, Layer } from "layerchart";
	import { onMount } from "svelte";

	let containerElement: HTMLDivElement;
	let containerWidth = 0;
	let containerHeight = 0;

	// Create date range for the past year
	const now = new Date();
	const firstDayOfYear = timeYear.floor(now);

	// Calculate optimal display parameters based on container size
	$: weeksToShow = containerWidth > 0 ? Math.floor((containerWidth - 32) / 12) : 53; // 32px for padding, ~12px per week
	$: cellSize =
		containerHeight > 0
			? Math.min((containerHeight - 32) / 7, (containerWidth - 32) / weeksToShow)
			: 10;

	// Calculate the actual date range to display - use a full year but anchor to right
	$: displayStartDate = (() => {
		// Always show a full year of data, but we'll anchor it to the right
		const yearStart = new Date(now.getFullYear(), 0, 1);
		return yearStart;
	})();

	// Calculate the end date - always use today
	$: displayEndDate = now;

	// Generate commit data for the display period
	$: commitData = (() => {
		const data: { date: Date; value: number | null }[] = [];
		const endDate = new Date(now);
		const daysBetween = Math.ceil(
			(endDate.getTime() - displayStartDate.getTime()) / (1000 * 60 * 60 * 24)
		);

		for (let i = 0; i <= daysBetween; i++) {
			const date = new Date(displayStartDate);
			date.setDate(date.getDate() + i);

			// Only include dates up to today
			if (date <= now) {
				// Simulate commit activity (some days have no commits)
				const hasCommits = Math.random() > 0.3;
				const commitCount = hasCommits ? Math.floor(Math.random() * 15) + 1 : null;

				data.push({
					date: date,
					value: commitCount,
				});
			}
		}

		return data;
	})();

	// Update container dimensions when mounted or resized
	const updateDimensions = () => {
		if (containerElement) {
			const rect = containerElement.getBoundingClientRect();
			containerWidth = rect.width;
			containerHeight = rect.height;
		}
	};

	onMount(() => {
		updateDimensions();
		window.addEventListener("resize", updateDimensions);

		return () => {
			window.removeEventListener("resize", updateDimensions);
		};
	});
</script>

<div class="relative flex-1/3 rounded-3xl bg-gray-900 after:absolute after:bottom-0 after:left-0 after:w-[calc(50%+1.5rem)] after:h-[1.5rem] after:rounded-bl-3xl after:pointer-events-none after:border-gray-500 after:border-b-1 after:border-l-1">
	<div bind:this={containerElement} class="absolute top-0 left-0 h-full w-full overflow-hidden p-4">
		{#if containerWidth > 0 && containerHeight > 0}
			<Chart
				data={commitData}
				x="date"
				c="value"
				cScale={scaleThreshold()}
				cDomain={[1, 3, 6, 10]}
				cRange={[
					"var(--color-primary-500)",
					"var(--color-primary-500)",
					"var(--color-primary-500)",
					"var(--color-primary-500)",
				]}
			>
				{#snippet children({ context })}
					<Layer type="html">
						<!-- Position calendar to anchor to the right -->
						<div style="position: relative; width: 100%; height: 100%;">
							<Calendar
								start={displayStartDate}
								end={displayEndDate}
								tooltipContext={context.tooltip}
								cellSize={[cellSize, cellSize]}
							>
								{#snippet children({ cells, cellSize: actualCellSize })}
									{#each cells as cell}
										<div
											class="absolute p-px"
											style:right="{containerWidth - 32 - cell.x - actualCellSize[0]}px"
											style:top="{cell.y}px"
											style:width="{actualCellSize[0]}px"
											style:height="{actualCellSize[1]}px"
											onpointermove={e => context.tooltip?.show(e, cell.data)}
											onpointerleave={e => context.tooltip?.hide()}
										>
											<div class="h-full w-full rounded-xs" style:background-color="#41414e">
												{#if cell.data?.value}
													<div
														class="h-full w-full rounded-xs"
														style:background-color="var(--color-primary-500)"
														style:opacity={Math.min(0.2 + (cell.data.value / 15) * 0.8, 1)}
													></div>
												{/if}
											</div>
										</div>
									{/each}
								{/snippet}
							</Calendar>
						</div>
					</Layer>

					<Tooltip.Root>
						{#snippet children({ data })}
							<div class="rounded bg-gray-700 px-2 py-1 text-xs text-white">
								<div class="font-medium">
									{data.date.toLocaleDateString("en-US", {
										weekday: "short",
										month: "short",
										day: "numeric",
									})}
								</div>
								{#if data.value != null}
									<div class="text-gray-300">
										{data.value} commit{data.value !== 1 ? "s" : ""}
									</div>
								{:else}
									<div class="text-gray-400">No commits</div>
								{/if}
							</div>
						{/snippet}
					</Tooltip.Root>
				{/snippet}
			</Chart>
		{/if}
	</div>
</div>