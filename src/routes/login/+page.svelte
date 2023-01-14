<script lang="ts">
	import { enhance } from '$app/forms';
	import { fade } from 'svelte/transition';

	let givenEmail: string = '';
	let givenPassword: string = '';
	let statusMessage: string | undefined = '';
</script>

<div class="entire-container">
	<div class="bg-image bg-image--dark" transition:fade />

	<div class="login-container" transition:fade>
		<h1>Welcome Back!</h1>

		<form method="POST" use:enhance>
			<input
				type="email"
				name="givenEmail"
				placeholder="Email"
				bind:value={givenEmail}
				class="input-form"
			/>

			<input
				type="password"
				id="password"
				name="givenPassword"
				placeholder="Password"
				bind:value={givenPassword}
				required
			/>

			<button class="btn-form">Log in With Password</button>

			<div class="status-message">{statusMessage}</div>
		</form>
	</div>

	<div class="right-side-content" />
</div>

<style>
	.entire-container {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
	}

	.login-container {
		position: absolute;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 400px;
		top: calc(var(--header-height) + 10%);
		left: 10%;
		margin: 0 auto;
		padding: 20px;
	}

	input {
		margin: 10px;
		padding: 10px;
		width: 100%;
		box-sizing: border-box;
		font-size: 14px;
		color: #333;
		border: 1px solid #ccc;
		border-radius: 13px;
	}

	.btn-form {
		margin: 20px 0 0;
		padding: 10px;
		width: 80%;
		box-sizing: border-box;
		font-size: 14px;
		font-weight: bold;
		color: #fff;
		background-color: #333;
		border: 0;
		cursor: pointer;
		border-radius: 13px;
	}

	.status-message {
		margin: 10px;
		padding: 0;
		display: block;
	}
</style>
