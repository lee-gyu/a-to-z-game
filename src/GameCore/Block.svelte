<script lang="ts" module>
const lvToText = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
</script>

<script lang="ts">
import type { BlockObject } from "./type";

type Props = {
	blockOject: BlockObject;
};

const props: Props = $props();
const { blockOject } = props;
</script>

<div class="block-obj">{lvToText[blockOject.level]}</div>

<style>
.block-obj {
    transition: top 0.15s, left 0.15s;
    position: absolute;
    display: flex;
    top: 10px;
    left: 10px;
    width: calc(var(--block-size) - 20px);
    height: calc(var(--block-size) - 20px);
    font-size: 2rem;
    align-items: center;
    justify-content: center;
    user-select: none;

    border: 4px solid black;
    background-color: var(--letter-lv-0);
}
</style>