<template>
	<div class="skills-info-wrapper pt-2 pb-2">
		<div class="col-12 text-center fw-bold">
			Languages
		</div>
		<!-- <div v-for="language in sortedLanguages" :key="language.name">
			<p class="fs-4 text-center">{{ language.name }}</p>
			<div class="progress mx-4" style="height: 5px;">
				<div
					class="progress-bar bg-success"
					role="progressbar"
					:aria-valuenow="language.confidence"
					:style="`width: ${getPercentage(language.confidence)}%`"
					aria-valuemin="0"
					aria-valuemax="10"
				></div>
			</div>
		</div> -->
		<div class="skills row">
			<div class="col-12 fs-6 ms-4 fw-bold pt-2">
				Confident In
			</div>
			<div
				class="col-6 fs-6 mt-2 text-center"
				v-for="language in confidentLanguages"
				:key="language.name"
			>
				{{ language.name }}
			</div>
		</div>
		<div class="skills row">
			<div class="col-12 fs-6 mt-4 ms-4 fw-bold pt-2">
				Familiar With
			</div>
			<div
				class="col-6 fs-6 mt-2 text-center"
				v-for="language in familiarLanguages"
				:key="language.name"
			>
				{{ language.name }}
			</div>
		</div>

		<hr />
		<div class="skills row pt-2">
			<div class="col-12 text-center fw-bold">
				Technologies
			</div>
			<div
				class="col-6 fs-6 text-center pt-1 pb-1"
				v-for="skill in skills"
				:key="skill"
			>
				{{ skill }}
			</div>
		</div>
	</div>
</template>

<script>
import _ from "lodash";
export default {
	name: "SkillsInfo",
	props: {
		languages: Array,
		skills: Array
	},
	data: () => ({
		sortedLanguages: [],
		confidentLanguages: [],
		familiarLanguages: []
	}),
	mounted() {
		this.sortedLanguages = _.orderBy(
			this.languages,
			["confidence", "name"],
			["desc"]
		);
		this.confidentLanguages = _.filter(
			this.sortedLanguages,
			language => language.confidence > 6
		);

		this.familiarLanguages = _.filter(
			this.sortedLanguages,
			language => language.confidence < 7
		);
	},
	methods: {
		getPercentage(confidence) {
			if (confidence < 5) {
				return 55;
			}
			if (confidence < 7) {
				return 75;
			}
			return 95;
		}
	}
};
</script>

<style></style>
