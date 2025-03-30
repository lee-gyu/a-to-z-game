<script lang="ts">
import { getContext } from "svelte";
import type { BlockObject } from "./type";
import Block from "./Block.svelte";

const objectList = getContext<BlockObject[]>("objectList");
</script>

<div class="board">
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    <div class="block-bg"></div>
    {#each objectList as blockObject (blockObject.id)}
        <Block blockOject={blockObject} />
    {/each}
</div>

<style>
    .board {
        --block-size: 120px;
        --border-size: 6px;
        --block-count: 4;
        border-radius: 16px;
        overflow: hidden;
        position: relative;
        display: inline-grid;
        background-color: var(--board-border-color);
        gap: var(--border-size);
        grid-template-columns: repeat(var(--block-count), var(--block-size));
        grid-template-rows: repeat(var(--block-count), var(--block-size));
        width: auto;
        border: var(--border-size) solid var(--board-border-color);
    }

    .block-bg {
        background-color: var(--background-color);
    }
</style>