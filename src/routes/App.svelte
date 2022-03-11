<script>

	let name = 'world';
	
</script>


<style>
	:global(body){
		padding: 0;
	}
</style>


<!-- "Body" -->
<div class="flex flex-row m-0 w-full h-full bg-warm-800">
	<!-- Side Bar -->
	<div class="bg-dark-300 text-black w-2/15 max-w-45 overflow-x-hidden overflow-y-scroll h-auto">
		<div class="flex flex-col">
			<div class="flex border-b-1 items-center border-dark-400 text-center h-10 pl-2 pr-2">
				<div class="pr-1">
					LOGO
				</div>
				<div>NAME</div>
			</div>
			<div class="group flex flex-row justify-start h-4 transition-all ease-linear delay-100 duration-200 hover:(bg-dark-200 h-5) active:(bg-dark-50 h-6)">
				<div class="w-10/10 transition-all ease-linear delay-100 duration-200 group-hover:w-5/10 group-active:w-1/10"></div>
				<svg class="transition-all ease-linear delay-100 duration-200 w-4 h-4 group-hover:(animate-pulse animate-duration-1000 w-5 h-5) group-active:(animate-pulse animate-duration-500 w-6 h-6)"  viewBox="0 0 24 24"><path fill="#888888" d="M14.71 15.88L10.83 12l3.88-3.88a.996.996 0 1 0-1.41-1.41L8.71 11.3a.996.996 0 0 0 0 1.41l4.59 4.59c.39.39 1.02.39 1.41 0c.38-.39.39-1.03 0-1.42z"></path></svg>
			</div>
			<div class="border-t-1 border-dark-400">
				Bar Content
			</div>
		</div>
	</div>

	<!-- Main Content -->
	<div class="bg-true-gray-800 text-black w-full">
		Main Content
	</div>
</div>