<template>
	<div id="app">
		<div class="page row page-wrapper">
			<div class="col-12">
				<user-info
					:name="information.name"
					:contact="information.contact"
				></user-info>
				<hr style="margin-top: 0; margin-bottom: 0;" />
				<educations-info :educations="information.educations">
				</educations-info>
				<hr />
				<!-- <p class="fs-5 text-center" v-html="information.tagline"></p> -->
				<!-- <hr /> -->
				<!--
				<hr />
				 -->
				<experiences-info
					:experiences="information.experiences"
				></experiences-info>
			</div>
		</div>
		<div class="page row page-wrapper">
			<div class="col-12 pt-4">
				<skills-info
					:languages="information.languages"
					:skills="information.skills"
				></skills-info>
				<hr />
				<projects-info :projects="information.projects"> </projects-info>
			</div>
		</div>
	</div>
</template>

<script>
import information from "./data/main.json";
import UserInfo from "./components/UserInfo";
import SkillsInfo from "./components/SkillsInfo";
import ExperiencesInfo from "./components/ExperiencesInfo";
import EducationsInfo from "./components/EducationsInfo";
import ProjectsInfo from "./components/ProjectsInfo";

export default {
	name: "App",
	props: {
		information: {
			type: Object,
			default: () => {
				return information;
			}
		}
	},
	components: {
		UserInfo,
		SkillsInfo,
		ExperiencesInfo,
		EducationsInfo,
		ProjectsInfo
	}
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
}

.page-wrapper {
	--bs-gutter-x: 0;
}

.side-info {
	/* background: linear-gradient(to right, #3fb984 0%, #ffffff 100%); */
	border-right: solid #ccc 1px;
}
</style>
