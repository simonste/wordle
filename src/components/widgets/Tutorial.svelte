<script lang="ts">
	import { COLS, ROWS } from "../../utils";

	import { Tile } from "../board";
	export let visible: boolean;
</script>

<h3>Spielanleitung</h3>
<div>Errate das <strong>WORDLE</strong> in {ROWS} versuchen.</div>
<div>Jeder Versuch muss ein gültiges {COLS}-Buchstabiges Wort sein.</div>
<div>
	Nach jedem Versuch zeigt die Farbe des Buchstabens an, wie gut dieser war.
</div>
<div class:complete={visible} class="examples">
	<div><strong>Beispiele</strong></div>
	<div class="row">
		<Tile value="B" state="🟩" />
		<Tile value="a" state="🔳" />
		<Tile value="u" state="🔳" />
		<Tile value="e" state="🔳" />
		<Tile value="r" state="🔳" />
	</div>
	<div>Der Buchstabe <strong>B</strong> ist im Lösungswort und an derselben Stelle.</div>
	<div class="row">
		<Tile value="p" state="🔳" />
		<Tile value="e" state="🟨" />
		<Tile value="n" state="🔳" />
		<Tile value="i" state="🔳" />
		<Tile value="s" state="🔳" />
	</div>
	<div>Der Buchstabe <strong>E</strong> ist im Lösungswort aber nicht an derselben Stelle.</div>
</div>
<div>
	Dies ist eine Kopie vom original <a
		href="https://www.powerlanguage.co.uk/wordle/"
		target="_blank">Wordle</a
	>
	von Josh Wardle. Der Kopie wurde von <a href="https://github.com/MikhaD" target="_blank">MikhaD</a> erstellt.
</div>

<style lang="scss">
	div {
		margin: 14px 0;
	}
	.examples {
		border-top: 1px solid var(--border-primary);
		border-bottom: 1px solid var(--border-primary);
		:global(.row > *) {
			height: 100%;
			aspect-ratio: 1;
		}
		&:not(.complete) :global(.row .back) {
			transition-delay: 0.3s;
		}
	}
	.row {
		height: 40px;
		display: flex;
		gap: 4px;
	}
</style>
