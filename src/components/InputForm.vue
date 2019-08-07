<template>
	<v-container fluid>
		<v-layout column>
			<!-- <v-layout row wrap justify-space-around>
			<v-switch v-model="valid" class="ma-3" label="Valid" readonly></v-switch>
			<v-switch v-model="lazy" class="ma-3" label="Lazy"></v-switch>
			</v-layout>-->
			<v-flex>
				<v-card class="pa-3 mx-2 my-3" color="grey lighten-3" id="dashboard">
					<v-card class="pa-3">
						<v-layout wrap>
							<v-flex xs12 sm12 md7 lg7 xl7>
								<!-- <v-card>
					<v-img :src="require('../assets/GetNow.png')" min-width="50%"></v-img>
								</v-card>-->

								<v-card flat color="transparent" class="ma-0">
									<v-card-title class="display-1 align-left font-weight-regular pa-2">Shop Plans Today</v-card-title>
								</v-card>
								<v-divider></v-divider>
								<v-card flat color="transparent" class="ma-5">
									<v-img :src="require('../assets/uhc.png')" max-width="50%"></v-img>
								</v-card>

								<v-card flat color="amber--text" class="ma-0">
									<v-card-title class="headline align-left font-weight-black pa-2">Shop Term Health Plans</v-card-title>
								</v-card>

								<v-card flat color="transparent" class="mt-4 ma-3 body-1 font-weight-medium">
									<p>
										&nbsp; &nbsp; &nbsp; Coverage when you need it, we deal specially in short term health insurance.
										Short term health insurance is a great way for people to fill gaps in insurance coverage
										without sacrificing routine healthcare services. In some cases, you can get coverage as
										soon as tomorrow and can cancel anytime without a termination penalty. Plus, short term
										plans offer a range of deductibles making it easy to find the right benefits at the right
										price
									</p>
								</v-card>
								<v-card flat outlined max-height="15em" class="ma-auto pa-3 mb-4" color="grey lighten-4">
									<v-card max-height="15em" class="mx-auto px-3 text-center" color="blue lighten-3">
										<v-card-title class="justify-center subtitle-1">
											Have Questions about &nbsp;
											<strong>Short-Term Health Plans?</strong>
										</v-card-title>
										<v-card-title
											class="justify-center title font-weight-black pt-0"
											color="light blue darken-4"
										>(877) 342-4747</v-card-title>
									</v-card>
								</v-card>
							</v-flex>

							<v-flex xs12 sm12 md5 lg5 xl5>
								<v-card
									flat
									color="light blue darken-4"
									max-width="40em"
									max-height="15em"
									class="mx-auto px-3 text-center"
								>
									<v-card-title class="justify-center title white--text">Get a Short-Term Quote Now</v-card-title>
								</v-card>
								<v-card flat color="transparent" class="pa-4">
									<v-form ref="form" v-model="valid" :lazy-validation="lazy">
										<v-text-field v-model="fname" :rules="nameRules" label="First Name" required></v-text-field>

										<v-text-field v-model="femail" :rules="emailRules" label="E-mail"></v-text-field>

										<v-text-field v-model="fnumber" label="Mobile Number" required></v-text-field>
										<!-- form -->
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
											<v-flex xs6 md6 lg2>
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

										<v-btn :disabled="!valid" color="success" class="mr-3" @click="validate">Shop Plans Now</v-btn>
									</v-form>
								</v-card>
							</v-flex>
						</v-layout>
					</v-card>
				</v-card>
			</v-flex>

			<!-- ======================================================== -->
			<v-flex>
				<v-card class="pa-3 mx-2 my-3" color="grey lighten-3">
					<v-layout wrap>
						<v-flex xs12 sm12 md4 lg4 xl4>
							<v-card flat min-height="1em" color="blue" class="ma-0"></v-card>
							<v-card flat color="blue lighten-5" max-width="40em" class="mx-auto px-3 text-center">
								<v-card-title
									class="justify-center title font-weight-black blue--text text--darken-4"
								>Short Term Plan Benefits:</v-card-title>
								<v-card-text>
									<ul class="subtitle-1 amber--text text--darken-2">
										<li>
											<span class="black--text font-weight-light">Lower Premiums</span>
										</li>
										<li>
											<span class="black--text font-weight-light">ER & Hospital Coverage</span>
										</li>
										<li>
											<span class="black--text font-weight-light">Doctor & Urgent Care Visits</span>
										</li>
										<li>
											<span class="black--text font-weight-light">No Long Term Commitments</span>
										</li>
										<li>
											<span class="black--text font-weight-light">Flexible, Anytime Enrollment</span>
										</li>
									</ul>
								</v-card-text>
								<v-btn color="blue" class="white--text ma-3" @click="$vuetify.goTo('#dashboard')">Shop Plans</v-btn>
							</v-card>
						</v-flex>

						<v-flex xs12 sm12 md8 lg8 xl8>
							<v-card flat color="white" class="ml-3 pa-3">
								<v-card flat color="white" class="ma-0">
									<v-card-title
										class="display-1 align-left font-weight-light pa-2"
									>Short Term Health Insurance</v-card-title>
								</v-card>
								<v-card flat color="white" class="ma-0">
									<v-card-title
										class="headline align-left font-weight-regular pa-2 blue--text"
									>Major medical insurance isn't always an option for some</v-card-title>
								</v-card>

								<v-card flat color="white" class="mt-4 ma-3 body-1 font-weight-regular">
									<p>
										If you've missed the deadline for open enrollment, for example, or you just can't
										afford the premiums and deductibles that come with a traditional health insurance
										policy, then short term coverage might be a good alternative for you. As the name
										implies, short term health insurance – abbreviated to STHPs for short-term health
										plans – is temporary medical coverage. These plans are ideal for people in
										transition, whether you've changed jobs and need something to fill the gap between
										employer-sponsored coverage, you've just graduated college or been dropped from
										your parents' plan, or you've retired early but don't qualify for Medicare yet.
									</p>
								</v-card>

								<v-card flat class="mx-auto mt-5 px-3 mb-5">
									<v-layout row align-center wrap>
										<v-flex xs12 sm6 md3>
											<v-card class="text-xs-center pa-0" flat color="transparent">
												<v-icon style="font-size: 70px" class="blue--text text--darken-2">av_timer</v-icon>
												<v-card-text class="blue--text text--darken-2 title pa-1">Fast Quote and Application</v-card-text>
												<v-card-text class="font-italic pa-1">Get quotes in seconds, apply in just minutes</v-card-text>
											</v-card>
										</v-flex>

										<v-flex xs12 sm6 md3>
											<v-card class="text-xs-center pa-0" flat color="transparent">
												<v-icon style="font-size: 70px" class="blue--text text--darken-2">attach_money</v-icon>
												<v-card-text class="blue--text text--darken-2 title pa-1">Budget Friendly Plans</v-card-text>
												<v-card-text class="font-italic pa-1">Choose options to fit your needs and budget</v-card-text>
											</v-card>
										</v-flex>
										<v-flex xs12 sm6 md3>
											<v-card class="text-xs-center pa-0" flat color="transparent">
												<v-icon style="font-size: 70px" class="blue--text text--darken-2">today</v-icon>
												<v-card-text class="blue--text text--darken-2 title pa-1">Next Day Coverage</v-card-text>
												<v-card-text class="font-italic pa-1">Apply today for coverage starting tomorrow</v-card-text>
											</v-card>
										</v-flex>
										<v-flex xs12 sm6 md3>
											<v-card class="text-xs-center pa-0" flat color="transparent">
												<v-icon style="font-size: 70px" class="blue--text text--darken-2">check_box</v-icon>
												<v-card-text class="blue--text text--darken-2 title pa-1">Available Year Round</v-card-text>
												<v-card-text class="font-italic pa-1">No waiting for enrollment periods to apply</v-card-text>
											</v-card>
										</v-flex>
									</v-layout>
								</v-card>
								<v-card flat color="white" class="mt-4 ma-3 body-1 font-weight-regular">
									Before 2016, STHPs could last from 30 days to a full year in some states, but that has since
									changed. Now, short term health policies run from 30 days to under three months. They cover
									limited benefits, don't include pre-existing conditions and aren't guaranteed-issue or renewable.
									Unlike major medical policies, STHPs include maximum lifetime payout limits, and you must meet a
									deductible before the insurer will pay its portion. Plus, STHPs require you to see in-network
									providers. If you go outside the network, the plan won't cover your care unless it's a true
									emergency.
									<br />
									<br />Despite some obvious drawbacks, short term health insurance makes sense for certain people.
									Premiums are much lower for STHPs than for major medical policies, they cover a variety of
									benefits depending on the plan you choose, and they offer peace of mind if you don't have
									major medical insurance but need some kind of protection in place. Combined with other
									policies, like standalone critical illness protection, short term medical plans can form
									one part of a decent private benefits package.
								</v-card>
							</v-card>
						</v-flex>
					</v-layout>
				</v-card>
			</v-flex>

			<v-flex>
				<v-card flat class="pa-3 mx-4 font-italic" color="transparent">
					<v-card-text>
						<strong>*Disclaimer:</strong> This Website is not associated with Healthcare.gov.
						HealthNetwork is not a licensed agent or broker and cannot write insurance
						policies. HealthNetwork will connect consumers to one of its trusted partners
						to complete the enrollment process. Plan prices and details shown are our intial
						estimates. Our Trusted Partners will provide more definitive information.
					</v-card-text>
					<v-divider></v-divider>
				</v-card>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>
export default {
	data: () => ({
		valid: true,
		femail: "",
		fname: "",
		fnumber: "",
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