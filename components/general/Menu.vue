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

			<v-btn text rounded>
				<v-icon>mdi-moon-waning-crescent</v-icon>
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
						<v-list-item-title>{{ item.text }}</v-list-item-title>
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
							Sandra Adams
						</v-list-item-title>
						<v-list-item-subtitle>
							sandra_a88@gmail.com
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

<script> //  moon-full
export default {
	name: "TheMenu",
	data() {
		return {
			drawer: true,
			clipped: false,
			items: [
				{
					icon: 'mdi-apps',
					title: 'Panel',
					to: '/'
				},
				{
					icon: 'mdi-apps',
					title: 'Pozizyonlar',
					to: '/'
				},
				{
					icon: 'mdi-apps',
					title: 'Terminal',
					to: '/'
				},
				{
					icon: 'mdi-apps',
					title: 'Botlar',
					to: '/'
				},
				{
					icon: 'mdi-apps',
					title: 'Faturalandırma',
					to: '/'
				},
				{
					icon: 'mdi-apps',
					title: 'Profil',
					to: '/'
				},
				{
					icon: 'mdi-apps',
					title: 'İşlemlerim',
					to: '/'
				},
				{
					icon: 'mdi-apps',
					title: 'Güvenlik',
					to: '/'
				},
				{
					icon: 'mdi-apps',
					title: 'Bildirimler',
					to: '/'
				},
			],
			language: [
				{
					symbol: 'tr',
					text: 'Türkçe'
				},
				{
					symbol: 'en',
					text: 'İngilizce'
				}
			]
		}
	}
}
</script>
