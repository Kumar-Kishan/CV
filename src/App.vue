<template>
	<div id="app">
		<div class="page row page-wrapper">
			<div class="col-4 side-info">
				<user-info
					:name="information.name"
					:contact="information.contact"
				></user-info>
				<hr />
				<p class="fs-5 text-center" v-html="information.tagline"></p>
				<hr />
				<educations-info :educations="information.educations">
				</educations-info>
				<hr />
				<skills-info
					:languages="information.languages"
					:skills="information.skills"
				></skills-info>
			</div>
			<div class="col-8 main-info">
				<experiences-info
					:experiences="information.experiences"
				></experiences-info>
				<projects-info :projects="information.projects"> </projects-info>
			</div>
		</div>
	</div>
</template>

<script>
import information from "./data/cv.json";
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
	background: linear-gradient(to right, #00ffff 0%, #ccffff 100%);
	height: 31cm;
	min-height: 31cm;
}
</style>
