<template>
	<div>
		<v-app-bar
			:clipped-left="clipped"
			fixed
			app
		>
			<v-app-bar-nav-icon @click.stop="drawer = !drawer"/>
			<v-spacer />
			<v-btn text rounded>
				<v-icon>mdi-account</v-icon>
			</v-btn>

			<v-btn text rounded @click="darkMode">
				<v-icon>{{iconDarkModeType}}</v-icon>
			</v-btn>
			<v-menu offset-y>
				<template v-slot:activator="{ on, attrs }">
					<v-btn
						text
						v-bind="attrs"
						v-on="on"
					>
						<v-icon>mdi-cog-outline</v-icon>
						<v-icon>mdi-chevron-down</v-icon>
					</v-btn>
				</template>
				<v-list>
					<v-list-item
						v-for="(item, index) in language"
						:key="index"
					>
						<v-img :src="item.url" width="40" />
						<v-list-item-title class="ml-2">{{ item.text }}</v-list-item-title>
					</v-list-item>
				</v-list>
			</v-menu>
			<v-btn text rounded>
				Sign out
			</v-btn>
		</v-app-bar>
		<v-navigation-drawer
			v-model="drawer"
			fixed
			app
		>
			<v-list>
				<v-list-item link>
					<v-list-item-content>
						<v-list-item-title class="text-h6">
							Ali Yılmaz
						</v-list-item-title>
						<v-list-item-subtitle>
							aliyilmaz@gmail.com
						</v-list-item-subtitle>
					</v-list-item-content>
				</v-list-item>
			</v-list>
			<v-divider></v-divider>
			<v-list>
				<v-list-item
					v-for="(item, i) in items"
					:key="i"
					:to="item.to"
					router
					exact
				>
					<v-list-item-action>
						<v-icon>{{ item.icon }}</v-icon>
					</v-list-item-action>
					<v-list-item-content>
						<v-list-item-title v-text="item.title"/>
					</v-list-item-content>
				</v-list-item>
			</v-list>
		</v-navigation-drawer>
	</div>
</template>

<script>
export default {
	name: "TheMenu",
	data() {
		return {
			drawer: true,
			clipped: false,
			items: [
				{
					icon: 'mdi-speedometer',
					title: 'Panel',
					to: '/home'
				},
				{
					icon: 'mdi-view-stream-outline',
					title: 'Pozizyonlar',
					to: '/'
				},
				{
					icon: 'mdi-television',
					title: 'Terminal',
					to: '/'
				},
				{
					icon: 'mdi-robot-excited-outline',
					title: 'Botlar',
					to: '/'
				},
				{
					icon: 'mdi-credit-card-outline',
					title: 'Faturalandırma',
					to: '/'
				},
				{
					icon: 'mdi-account-circle-outline',
					title: 'Profil',
					to: '/'
				},
				{
					icon: 'mdi-swap-horizontal',
					title: 'İşlemlerim',
					to: '/'
				},
				{
					icon: 'mdi-shield-account-outline',
					title: 'Güvenlik',
					to: '/'
				},
				{
					icon: 'mdi-bell-outline',
					title: 'Bildirimler',
					to: '/'
				},
			],
			language: [
				{
					symbol: 'tr',
					text: 'Türkçe',
					url: 'https://countryflagsapi.com/svg/tr'
				},
				{
					symbol: 'en',
					text: 'English',
					url: 'https://countryflagsapi.com/svg/us'
				}
			]
		}
	},
	computed:{
		iconDarkModeType() {
			return this.$vuetify.theme.dark ? 'mdi-white-balance-sunny' : 'mdi-moon-waning-crescent'
		}
	},
	methods: {
		darkMode() {
			this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
		}
	}
}
</script>
