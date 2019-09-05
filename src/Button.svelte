<script>
	export let variant = null;
</script>

<style>
	.button { padding: 0.5rem; }
	.primary { background: #748DD5; border-color: #748DD5; color: #FFF; }
	.success { background: #75D37E; border-color: #75D37E; color: #FFF; }
</style>

<button
  class="button {variant}"
>
	<slot></slot>
</button>