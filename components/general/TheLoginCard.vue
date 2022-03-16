<template>
	<v-card
		ref="cardContainer"
		class="mx-auto pa-16"
		max-width="600"
	>

		<v-img
			:src="require('~/static/crypto-exchange.png')"
			:contain="true"
			height="200"
		/>

		<div class="mt-16 mb-12 text-h3 primary--text">Giriş Yap</div>

		<div v-if="!registerLoading">
			<div>
				<v-text-field
					v-model="userEmail"
					:placeholder="'Email'"
					required
					outlined
					:disabled="type !== 'register'"
				/>

				<v-text-field
					id="password-input"
					v-model="password"
					outlined
					:append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
					:type="show1 ? 'text' : 'password'"
					name="input-10-1"
					:placeholder="'Şifre'"
					@click:append="show1 = !show1"
				/>
			</div>

			<v-btn
				class="mt-4"
				outlined
				depressed
				large
				color="primary"
				block
				:disabled="btnStatus"
				@click="$router.push('/home')"
			>
				Giriş
			</v-btn>
			<div class="error--text">{{ errorMessage }}</div>
		</div>

		<div v-else class="d-flex flex-row justify-center">
			<v-progress-circular :size="50" color="primary" indeterminate/>
		</div>

		<v-dialog v-model="registerDialog" width="500">
			<v-card
				class="d-flex flex-column justify-space-between py-4"
				height="300"
				rounded
			>
				<v-card-title class="d-flex flex-column text-h3 success--text">
					Kayıt Başarılı
				</v-card-title>

				<v-row class="mx-0" align-content="center">
					<v-col class="px-0">
						<v-icon
							class="green lighten-5 rounded-icon"
							size="120"
							color="success"
						>
							mdi-check
						</v-icon>
					</v-col>
				</v-row>
				<v-card-actions class="d-flex flex-column">
					<div class="text-h6 success--text">Yönlendiriliyorsunuz...</div>
				</v-card-actions>
			</v-card>
		</v-dialog>
	</v-card>

</template>

<script>
export default {
	name: 'TheLoginCard',
	data() {
		return {
			registerLoading: false,
			userName: '',
			userEmail: '',
			password: '',
			type: 'register',
			errorMessage: '',
			show1: true,
			btnStatus: false,
			registerDialog: false
		}
	}
}
</script>
