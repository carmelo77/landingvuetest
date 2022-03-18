<template>
	<div>
		<div
			class="flex flex-row flex-wrap justify-start align-center gap-5"
			v-if="items.length > 0"
		>
			<!-- Product Card -->
			<div 
				v-for="(item, idx) in items"
				:key="`${idx}`"
				class="flex flex-col shadow-md cursor-pointer w-64 hover:-translate-y-1 duration-300"
			>
				<!-- Preview -->
				<div class="inline relative group h-48">
					<!-- Thumbnail -->
					<img class="absolute rounded-t object-cover h-full w-full"
							:src="`${item.image}`"
							alt="Product Preview" />

							<!-- Hover Bar -->
							<div class="flex flex-row absolute justify-end
								h-16 w-full bottom-0 px-3 space-x-2
								bg-none opacity-0 group-hover:opacity-100
								group-hover:bg-gradient-to-t from-black/20 via-gray-800/20 to-transparent 
								transition-all ease-in-out duration-200 delay-100">
							</div>
				</div>
				<!-- Body -->
				<div class="flex flex-col bg-white rounded-b p-5">
					<!-- Title -->
					<div class="text-md px-2 font-bold hover:underline">
						{{ item.title }}
					</div>

					<!-- Description text -->
					<div class="text-sm mx-2 text-semibold mt-1">
						{{ item.content }}
					</div>
				</div>
			</div>

			
			<!-- <div class="flex flex-col shadow-md cursor-pointer w-64 hover:-translate-y-1 duration-300">
				
				<div class="inline relative group h-48">
					
					<img class="absolute rounded-t object-cover h-full w-full"
							src="../assets/2.png"
							alt="Product Preview" />

							
							<div class="flex flex-row absolute justify-end
								h-16 w-full bottom-0 px-3 space-x-2
								bg-none opacity-0 group-hover:opacity-100
								group-hover:bg-gradient-to-t from-black/20 via-gray-800/20 to-transparent 
								transition-all ease-in-out duration-200 delay-100">
							</div>
				</div>
				
				<div class="flex flex-col bg-white rounded-b p-5">
				
					<div class="text-md px-2 font-bold hover:underline">
						Curabitur Vulputate placerat tristique nam libero eros
					</div>

					
					<div class="text-sm mx-2 text-semibold mt-1">
						Malesuada fortor, facilisi veii turpis ullacomper, Matiis, egestas matiis nullas pretium, arcu pretium, tempar.
					</div>
				</div>
			</div>

			
			<div class="flex flex-col shadow-md cursor-pointer w-64 hover:-translate-y-1 duration-300">
			
				<div class="inline relative group h-48">
					
					<img class="absolute rounded-t object-cover h-full w-full"
							src="../assets/1.png"
							alt="Product Preview" />

							
							<div class="flex flex-row absolute justify-end
								h-16 w-full bottom-0 px-3 space-x-2
								bg-none opacity-0 group-hover:opacity-100
								group-hover:bg-gradient-to-t from-black/20 via-gray-800/20 to-transparent 
								transition-all ease-in-out duration-200 delay-100">
							</div>
				</div>
				
				<div class="flex flex-col bg-white rounded-b p-5">
					
					<div class="text-md px-2 font-bold hover:underline">
						Curabitur Vulputate placerat tristique nam libero eros
					</div>

					
					<div class="text-sm mx-2 text-semibold mt-1">
						Malesuada fortor, facilisi veii turpis ullacomper, Matiis, egestas matiis nullas pretium, arcu pretium, tempar.
					</div>
				</div>
			</div>

			
			<div class="flex flex-col shadow-md cursor-pointer w-64 hover:-translate-y-1 duration-300">
			
				<div class="inline relative group h-48">
					
					<img class="absolute rounded-t object-cover h-full w-full"
							src="../assets/3.png"
							alt="Product Preview" />

							
							<div class="flex flex-row absolute justify-end
								h-16 w-full bottom-0 px-3 space-x-2
								bg-none opacity-0 group-hover:opacity-100
								group-hover:bg-gradient-to-t from-black/20 via-gray-800/20 to-transparent 
								transition-all ease-in-out duration-200 delay-100">
							</div>
				</div>
				
				<div class="flex flex-col bg-white rounded-b p-5">
					
					<div class="text-md px-2 font-bold hover:underline">
						Curabitur Vulputate placerat tristique nam libero eros
					</div>

					
					<div class="text-sm mx-2 text-semibold mt-1">
						Malesuada fortor, facilisi veii turpis ullacomper, Matiis, egestas matiis nullas pretium, arcu pretium, tempar.
					</div>
				</div>
			</div>

			
			<div class="flex flex-col shadow-md cursor-pointer w-64 hover:-translate-y-1 duration-300">
				
				<div class="inline relative group h-48">
					
					<img class="absolute rounded-t object-cover h-full w-full"
							src="../assets/2.png"
							alt="Product Preview" />

							
							<div class="flex flex-row absolute justify-end
								h-16 w-full bottom-0 px-3 space-x-2
								bg-none opacity-0 group-hover:opacity-100
								group-hover:bg-gradient-to-t from-black/20 via-gray-800/20 to-transparent 
								transition-all ease-in-out duration-200 delay-100">
							</div>
				</div>
				
				<div class="flex flex-col bg-white rounded-b p-5">
					
					<div class="text-md px-2 font-bold hover:underline">
						Curabitur Vulputate placerat tristique nam libero eros
					</div>

					
					<div class="text-sm mx-2 text-semibold mt-1">
						Malesuada fortor, facilisi veii turpis ullacomper, Matiis, egestas matiis nullas pretium, arcu pretium, tempar.
					</div>
				</div>
			</div> -->
			
		</div>
	</div>
</template>

<script>

export default {
	props: {
		items: {
			required: true,
			type: Array,
			default: [],
		}
	},
}
</script>