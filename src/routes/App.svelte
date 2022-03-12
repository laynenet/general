<script>
	import Collapsible from "./Collapsible.svelte";

	let name = 'Name';
	
	let sideBarOn = true;
	function sideBarSwap(){ sideBarOn=!sideBarOn; }

</script>


<style>
	:global(body){
		padding: 0;
	}
</style>


<!-- "Body" -->
<div class="flex flex-row m-0 w-full h-full bg-warm-800">
	<!-- Side Bar -->
	{#if sideBarOn}
	<!-- Opened Side Bar -->
	<div id="sideBar" class="bg-dark-300 text-black w-1/5 max-w-60 overflow-x-hidden overflow-x-hidden overflow-y-auto h-auto">
		<div class="flex flex-col">
			<!-- Image and Name -->
			<div class="flex border-b-1 items-center border-dark-400 text-center h-10 pl-2 pr-2">
				<div class="pr-1 h-full">
					<img class="rounded-full max-h-full p-1" src="/70004214.png" alt="">
				</div>
				<div class="text-light-900">{name}</div>
			</div>
			<!-- Close Side Bar -->
			<div class="group flex flex-row justify-start h-4 transition-all ease-linear delay-100 duration-200 hover:(bg-dark-200 h-5) active:(bg-dark-50 h-6) children:(transition-all ease-linear delay-100 duration-200)" on:click={sideBarSwap}>
				<div class="w-10/10  group-hover:w-5/10 group-active:w-1/10"></div>
				<svg class=" w-4 h-4 group-hover:(animate-pulse animate-duration-1000 w-5 h-5) group-active:(animate-pulse animate-duration-500 w-6 h-6)"  viewBox="0 0 24 24"><path fill="#888888" d="M14.71 15.88L10.83 12l3.88-3.88a.996.996 0 1 0-1.41-1.41L8.71 11.3a.996.996 0 0 0 0 1.41l4.59 4.59c.39.39 1.02.39 1.41 0c.38-.39.39-1.03 0-1.42z"></path></svg>
			</div>
			<!-- Bar Content -->
			<div class="border-t-1 border-dark-400 pt-1 pl-1 pr-1">
				<div class="flex flex-col">
					<div class="mb-1">#Bar Content</div>

					<Collapsible title="Title">
						<div>Data</div>
						<div>Data</div>
						<div>Data</div>
					</Collapsible>
					<Collapsible title="Title">
						<div>Data</div>
						<div>Data</div>
						<Collapsible title="Title">
							<div>Data</div>
							<div>Data</div>
							<div>Data</div>
						</Collapsible>
						<div>Data</div>
					</Collapsible>
				</div>
				
			</div>
		</div>
	</div>
	{:else}
	<!-- Closed Side Bar -->
	<div class="group bg-dark-300 w-4 max-w-60 h-full transition-all ease-linear duration-200 hover:(bg-dark-200) active:(bg-dark-50 w-1/5)" on:click={sideBarSwap}>
		<svg class="w-full h-full" viewBox="0 0 24 24"><path fill="#888888" d="M8.59 16.59L13.17 12L8.59 7.41L10 6l6 6l-6 6l-1.41-1.41z"></path></svg>
	</div>
	{/if}
	
	

	<!-- Main Content -->
	<div class="bg-true-gray-800 text-black w-full">
		Main Content
	</div>
</div>



