<template>
	<v-app>
		<v-toolbar app>
			<v-container pa-0 style="color:blue">
				<v-layout column >
					<v-flex text-xs-center >
						<div class="text-truncate" style="font-size: .60em">Speak with a representative now!</div>
					</v-flex>
					<v-flex text-xs-center>
						<div class="font-weight-bold" style="font-size: 2em">+1 877-342-4747</div>
					</v-flex>
				</v-layout>
			</v-container>
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
