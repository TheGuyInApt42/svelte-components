<style lang="scss" type="text/scss">
    // Color variables
    $blue: #056ef0;
    $primary-color: aqua;
    $hover-primary-color: #b33106;
    $primary-white: #fff;
    $primary-textcolor: rgba(0, 0, 0, 0.87);

    // Card Variables
    $card-transition: box-shadow 280ms cubic-bezier(0.4, 0, 0.2, 1);
    $card-box-shadow: 0 2px 1px -1px rgba(0, 0, 0, 0.2), 0 1px 1px 0 rgba(0, 0, 0, 0.14), 0 1px 3px 0 rgba(0, 0, 0, 0.12);
    $card-background-color: $primary-white;
    $card-text-color: $primary-textcolor;

	.svelte-starter-card {
		background: $card-background-color;
		color: $card-text-color;
		transition: $card-transition;
		display: block;
		position: relative;
		padding: 16px;
		border-radius: 4px;
		box-shadow: $card-box-shadow;
	}
</style>

<script>
</script>

<div class="svelte-starter-card" on:click>
	<slot name="card-content" />
</div>