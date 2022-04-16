<script>
	import QrCode from "svelte-qrcode"
	let value = 'https://github.com/emrekayik';

	function selectAll(){
		this.setSelectionRange(0, this.value.length)
	}

	$: background = '';
</script>

<main>
	<div class="card">
		<h1>QRCardEK</h1>
		<div class="image-area">
			<QrCode {value} background="#1f3251"/>
		</div>
		<input bind:value={value} on:focus={selectAll} placeholder="enter your url">
	</div>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100vh;
		width: 100%;
		margin: 0 auto;
	}
	.card{
		padding: 12px;
		border-radius: 5px;
		box-shadow: 0px 0px 5px 0px #1f3251;
		background-color: #1f3251;
		overflow: hidden;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 300px;
		resize: both;
	}

	@media (max-width: 375px) {
		main {
			max-width: none;
		}
	}
</style>