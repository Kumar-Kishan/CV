<template>
	<div class="experiences-info-wrapper">
		<div class="row">
			<p class="fs-2 ms-4 me-4 fs-italic underline">Experiences</p>
			<div
				class="experience"
				v-for="experience in experiences"
				:key="experience.company"
			>
				<div class="company pull-right me-4">
					<p class="fs-5">
						<i>{{ experience.company }}</i>
					</p>
				</div>
				<div
					class="position ms-2"
					v-for="role in experience.roles"
					:key="role.role"
				>
					<p class="fs-6 fw-bold">
						{{ role.role }} ({{ role.timeframe.from }} -
						{{ role.timeframe.to }})
					</p>

					<div v-if="role.responsibility">
						<ul>
							<li class="fs-6" v-for="resp in role.responsibility" :key="resp">
								<p>{{ resp }}</p>
							</li>
						</ul>
					</div>
					<div
						class="project-wrapper"
						style="margin-top: 4px;"
						v-if="role.projects"
					>
						<div v-for="project in role.projects" :key="project.name">
							<p class="fs-6 fst-italic text-decoration-underline">
								{{ project.name }}
							</p>
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
	</div>
</template>

<script>
export default {
	name: "ExperiencesInfo",
	props: {
		experiences: Array
	}
};
</script>

<style></style>
