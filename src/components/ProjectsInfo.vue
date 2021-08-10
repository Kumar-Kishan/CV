<template>
	<div class="projects-info-wrapper">
		<div class="row">
			<p class="fs-1 fw-bold ms-4 me-4 text-capitalize">
				Personal Projects
			</p>
			<hr class="ms-4" style="width: 92% !important; margin: 0;" />
			<div class="project" v-for="project in projects" :key="project.title">
				<div class="project ms-4" v-if="!project.hide">
					<p class="fs-6">
						<strong>{{ project.title }}</strong> ({{ project.description }})
					</p>
					<div v-if="project.responsibility">
						<ul>
							<li
								class="fs-6"
								v-for="resp in project.responsibility"
								:key="resp"
							>
								<p>{{ resp }}</p>
							</li>
						</ul>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "ProjectsInfo",
	props: {
		projects: {
			type: Array,
			default: () => []
		}
	}
};
</script>

<style></style>
