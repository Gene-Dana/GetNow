<template>
	<v-footer padless>
		<v-layout justify-center wrap>
			<v-flex lighten-2 pa-3 black--text xs6>
				&copy; {{ new Date().getFullYear() }} —
				<strong>Get Medical Insurance Now</strong>
			</v-flex>
			<v-btn v-for="link in links" :key="link" color="black" flat xs6 class="my-2">{{ link }}</v-btn>
		</v-layout>
	</v-footer>
</template>

<script>
export default {
	data: () => ({
		links: ["Privacy Policy", "Terms & Conditions"]
	})
};
</script>
