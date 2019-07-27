<template>
	<v-app>
		<v-toolbar app>
			<v-toolbar-side-icon>
				<v-img :src="require('./assets/icon.png')" left></v-img>
			</v-toolbar-side-icon>

			<v-toolbar-title>Get Medical Insurance Now</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-toolbar-items class="hidden-sm-and-down">
				<v-btn large flat>+1 877-342-4747</v-btn>

			</v-toolbar-items>
		</v-toolbar>


		<v-content>
			<InputForm />
		</v-content>
	</v-app>
</template>

<script>
import InputForm from "./components/InputForm";

export default {
	name: "App",
	metaInfo: {
		title: "My Example App",
		titleTemplate: "%s - Yay!",
		htmlAttrs: {
			lang: "en",
			amp: true
		}
	},
	components: {
		InputForm
	},
	data() {
		return {
			//
		};
	}
};
</script>
