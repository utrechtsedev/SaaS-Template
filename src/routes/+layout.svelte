<script>
	import "../app.css";
	let { children } = $props();
</script>

<div class="app">
	<!-- Make header sticky at the top -->
	<header class="sticky top-0 z-[999] flex justify-center">
		<div
			class="navbar w-full xl:w-6/12 bg-gray-700/30 rounded-full m-4 pr-8 backdrop-blur-xl border border-gray-700"
		>
			<div class="navbar-start">
				<!-- <div class="dropdown">
					<div
						tabindex="0"
						role="button"
						class="btn btn-ghost lg:hidden"
					>
						<svg
							xmlns="http://www.w3.org/2000/svg"
							class="h-5 w-5"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M4 6h16M4 12h8m-8 6h16"
							/>
						</svg>
					</div>
					<ul
						tabindex="0"
						class="menu menu-sm dropdown-content bg-base-100 rounded-box z-[1] mt-3 w-52 p-2 shadow"
					>
						<li><a>Item 1</a></li>
						<li>
							<a>Parent</a>
							<ul class="p-2">
								<li><a>Submenu 1</a></li>
								<li><a>Submenu 2</a></li>
							</ul>
						</li>
						<li><a>Item 3</a></li>
					</ul>
				</div> -->
				<!-- svelte-ignore a11y_missing_attribute -->
				<a class="btn btn-ghost text-xl rounded-full">Innovatieweb</a>
			</div>

			<div class="navbar-center hidden lg:flex">
				<!-- <ul class="menu menu-horizontal px-1">
			<li><a>Item 1</a></li>
			<li>
			  <details>
				<summary>Parent</summary>
				<ul class="p-2">
				  <li><a>Submenu 1</a></li>
				  <li><a>Submenu 2</a></li>
				</ul>
			  </details>
			</li>
			<li><a>Item 3</a></li>
		  </ul> -->
			</div>

			<div class="navbar-end">
				<a
					href="https://github.com/utrechtsedev"
					target="_blank"
					class="rounded-full px-3 py-3 bg-black/20 border border-gray-600"
				>
					<svg
						class="inline-flex"
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
					>
						<path
							fill="currentColor"
							d="M12 2A10 10 0 0 0 2 12c0 4.42 2.87 8.17 6.84 9.5c.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34c-.46-1.16-1.11-1.47-1.11-1.47c-.91-.62.07-.6.07-.6c1 .07 1.53 1.03 1.53 1.03c.87 1.52 2.34 1.07 2.91.83c.09-.65.35-1.09.63-1.34c-2.22-.25-4.55-1.11-4.55-4.92c0-1.11.38-2 1.03-2.71c-.1-.25-.45-1.29.1-2.64c0 0 .84-.27 2.75 1.02c.79-.22 1.65-.33 2.5-.33s1.71.11 2.5.33c1.91-1.29 2.75-1.02 2.75-1.02c.55 1.35.2 2.39.1 2.64c.65.71 1.03 1.6 1.03 2.71c0 3.82-2.34 4.66-4.57 4.91c.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0 0 12 2"
						/>
					</svg>
					Github
				</a>
			</div>
		</div>
	</header>

	<main>
		{@render children()}
	</main>
	<footer></footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		background-color: #0b0b0d;
	}
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}
	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}
</style>
