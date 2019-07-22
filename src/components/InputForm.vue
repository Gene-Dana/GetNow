<template>
	<v-container pa-3>
		<v-layout wrap justify-center>
			<!-- <v-layout row wrap justify-space-around>
			<v-switch v-model="valid" class="ma-3" label="Valid" readonly></v-switch>
			<v-switch v-model="lazy" class="ma-3" label="Lazy"></v-switch>
			</v-layout>-->
			<v-flex xs12 sm6 md8>
				<v-card>
					<v-img :src="require('../assets/GetNow.png')" min-width="50%"></v-img>
				</v-card>

				<v-card flat color=transparent class="mt-4">
					<p> &nbsp; &nbsp; &nbsp; Coverage when you need it, we deal specially in short term health insurance.
						Short term health insurance is a great way for people to fill gaps in insurance coverage 
						without sacrificing routine healthcare services. In some cases, you can get coverage as 
						soon as tomorrow and can cancel anytime without a termination penalty. Plus, short term 
						plans offer a range of deductibles making it easy to find the right benefits at the right 
						price</p>
				</v-card>
				<v-card flat color="transparent">
					<v-form ref="form" v-model="valid" :lazy-validation="lazy">
						<v-text-field v-model="name" :rules="nameRules" label="Name" required></v-text-field>

						<v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>

						<v-layout>
							<v-flex xs12 md6 lg2>
								<v-select
									v-model="select"
									:items="tobacco"
									:rules="[v => !!v || 'Item is required']"
									label="Tobacco Use"
									required
								></v-select>
							</v-flex>
							<v-flex xs12 md6 lg2>
								<v-select
									v-model="select"
									:items="gender"
									:rules="[v => !!v || 'Item is required']"
									label="Gender"
									required
								></v-select>
							</v-flex>
						</v-layout>

						<v-layout align-center justify-center row fill-height>
							<v-flex xs12 md6>
								<v-select
									v-model="selectMonth"
									:items="month"
									:rules="[v => !!v || 'Item is required']"
									label="Month"
									required
								></v-select>
							</v-flex>
							<v-flex xs12 md6>
								<v-select
									v-model="selectDay"
									:items="day"
									:rules="[v => !!v || 'Item is required']"
									label="Day"
									required
								></v-select>
							</v-flex>
							<v-flex xs12 md6>
								<v-select
									v-model="selectYear"
									:items="year"
									:rules="[v => !!v || 'Item is required']"
									label="Year"
									required
								></v-select>
							</v-flex>
						</v-layout>

						<v-layout>
							<v-flex md-6>
								<v-checkbox v-model="checkbox2" label="Include Spouse?"></v-checkbox>
							</v-flex>

							<v-flex md-6>
								<v-checkbox v-model="checkbox3" label="Include Children?"></v-checkbox>
							</v-flex>
						</v-layout>
						<div class="font-italic">
							DISCLAIMER: By submitting your information you expressly consent
							to receiving phone calls, e-mails and SMS messages from ProDesk,
							it's subsidiaries and/or one of it's trusted partners at the phone
							number or email listed above to provide you quotes for health insurance.
							You understand that your consent to being contacted does not 
							require you to purchase a health insurance plan. Receiving quotes from 
							ProDesk is always free. Additional charges may apply to SMS, call or 
							Internet usage depending on your data providers. You can opt out of 
							receiving future messages from HealthNetwork.
						</div>
						<v-checkbox
							v-model="checkbox1"
							:rules="[v => !!v || 'You must agree to continue!']"
							label="Do you agree?"
							required
						></v-checkbox>

						<v-btn :disabled="!valid" color="success" class="mr-3" @click="validate">Submit</v-btn>
					</v-form>
				</v-card>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>
export default {
	data: () => ({
		valid: true,
		name: "",
		nameRules: [
			v => !!v || "Name is required",
			v => (v && v.length <= 20) || "Name must be less than 10 characters"
		],
		email: "",
		emailRules: [
			v => !!v || "E-mail is required",
			v => /.+@.+\..+/.test(v) || "E-mail must be valid"
		],
		select: null,
		selectMonth: null,
		selectDay: null,
		selectYear: null,

		tobacco: ["Yes", "No"],
		gender: ["Female", "Male", "I prefer not to say"],
		month: [
			"January",
			"February",
			"March",
			"April",
			"May",
			"June",
			"July",
			"August",
			"September",
			"October",
			"November",
			"December"
		],
		day: [
			"1",
			"2",
			"4",
			"5",
			"6",
			"7",
			"8",
			"9",
			"10",
			"11",
			"12",
			"13",
			"14",
			"15",
			"16",
			"17",
			"18",
			"19",
			"20",
			"21",
			"22",
			"23",
			"24",
			"25",
			"26",
			"27",
			"28",
			"29",
			"30",
			"31"
		],
		year: [
			"2019",
			"2018",
			"2017",
			"2016",
			"2015",
			"2014",
			"2013",
			"2012",
			"2011",
			"2010",
			"2009",
			"2008",
			"2007",
			"2006",
			"2005",
			"2004",
			"2003",
			"2002",
			"2001",
			"2000",
			"1999",
			"1998",
			"1997",
			"1996",
			"1995",
			"1994",
			"1993",
			"1992",
			"1991",
			"1990",
			"1989",
			"1988",
			"1987",
			"1986",
			"1985",
			"1984",
			"1983",
			"1982",
			"1981",
			"1980",
			"1979",
			"1978",
			"1977",
			"1976",
			"1975",
			"1974",
			"1973",
			"1972",
			"1971",
			"1970",
			"1969",
			"1968",
			"1967",
			"1966",
			"1965",
			"1964",
			"1963",
			"1962",
			"1961",
			"1960",
			"1959",
			"1958",
			"1957",
			"1956",
			"1955",
			"1954",
			"1953",
			"1952",
			"1951",
			"1950",
			"1949",
			"1948",
			"1947",
			"1946",
			"1945",
			"1944",
			"1943",
			"1942",
			"1941",
			"1940",
			"1939",
			"1938",
			"1937",
			"1936",
			"1935",
			"1934",
			"1933",
			"1932",
			"1931",
			"1930",
			"1929",
			"1928",
			"1927",
			"1926",
			"1925",
			"1924",
			"1923",
			"1922",
			"1921",
			"1920",
			"1919",
			"1918",
			"1917",
			"1916",
			"1915",
			"1914",
			"1913",
			"1912",
			"1911",
			"1910",
			"1909",
			"1908",
			"1907",
			"1906",
			"1905",
			"1904",
			"1903",
			"1902",
			"1901",
			"1900"
		],
		checkbox1: false,
		checkbox2: false,
		checkbox3: false,
		lazy: false
	}),

	methods: {
		validate() {
			if (this.$refs.form.validate()) {
				this.snackbar = true;
			}
		},
		reset() {
			this.$refs.form.reset();
		},
		resetValidation() {
			this.$refs.form.resetValidation();
		}
	}
};
</script>