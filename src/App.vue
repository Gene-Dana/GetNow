<template>
	<v-app>
		<Navvy />

		<v-content>
			<InputForm />
			<Footer />
		</v-content>
	</v-app>
</template>

<script>
import InputForm from "./components/InputForm";
import Footer from "./components/Footer";
import Navvy from "./components/Navvy"

export default {
	name: "App",
	metaInfo: {
		title: "Get Medical Insurance Now",
		titleTemplate: "%s - Yay!",
		htmlAttrs: {
			lang: "en",
			amp: true
		}
	},
	components: {
		InputForm,
		Footer,
		Navvy
	},
	data() {
		return {
			//
		};
	}
};
</script>
