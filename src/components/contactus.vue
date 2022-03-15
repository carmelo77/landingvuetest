<template>
	<div>
		<div class="form w-3/4 m-auto flex flex-wrap justify-around">
		
			<div class="flex flex-col space-y-2 w-5/12 py-2">
				<label for="default" class="select-none font-bold uppercase">Nombre</label>
				<input
					id="name"
					type="text"
					name="name"
					v-model="form.name"
					class="px-4 py-2 border border-gray-300 focus:outline-none focus:ring-2 focus:ring-gray-200"
				/>
			</div>

			<div class="flex flex-col space-y-2 w-5/12 py-2">
				<label for="default" class="select-none font-bold uppercase">Apellido</label>
				<input
					id="lastname"
					type="text"
					name="lastname"
					v-model="form.lastname"
					class="px-4 py-2 border border-gray-300 focus:outline-none focus:ring-2 focus:ring-gray-200"
				/>
			</div>

			<div class="flex flex-col space-y-2 w-5/12 py-2">
				<label for="default" class="select-none font-bold uppercase">Mail</label>
				<input
					id="email"
					type="email"
					name="email"
					v-model="form.email"
					class="px-4 py-2 border border-gray-300 focus:outline-none focus:ring-2 focus:ring-gray-200"
				/>
			</div>

			<div class="flex flex-col space-y-2 w-5/12 py-2">
				<label for="default" class="select-none font-bold uppercase">Telefono</label>
				<input
					id="phone"
					type="text"
					name="phone"
					v-model="form.phone"
					class="px-4 py-2 border border-gray-300 focus:outline-none focus:ring-2 focus:ring-gray-200"
				/>
			</div>

		</div>
		<div class="form w-3/4 m-auto flex justify-end py-12">
			<button class="btn-gold w-32 py-2 rounded-full mx-10" @click.prevent="send">Enviar</button>
		</div>
	</div>
</template>

<script>
import { BASE_URL } from '../api/api';

export default {
	data() {
		return {
			form: {
				name: '',
				lastname: '',
				email: '',
				phone: ''
			}
		}
	},

	methods: {
		send() {
			const params = {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				},
				body: JSON.stringify(this.form)
			}

			fetch(`${BASE_URL}/newsletter`, params).then(res => {
				return res.json();
			})
			.then(response => {
				console.log(response);
				this.$swal( 'Has enviado tu mensaje éxitosamente.' );
				this.clear();
			})
			.catch(err => console.log(err))
		},

		clear() {
			this.form.name = "";
			this.form.lastname = "";
			this.form.email = "";
			this.form.phone = "";
		}
	}
}
</script>
</script>