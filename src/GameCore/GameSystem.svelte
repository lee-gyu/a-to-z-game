<script lang="ts">
import Board from "./Board.svelte";
import { setContext } from "svelte";
import type { BlockObject } from "./type";

const objectList = $state<BlockObject[]>([
	{
		id: 0,
		level: 0,
		x: 0,
		y: 0,
	},
]);

setContext("objectList", objectList);
</script>

<div class="game-system">
    <Board/>
</div>

<style>
.game-system {
    display: flex;
    justify-content: center;;
    padding: 20px;
}
</style>