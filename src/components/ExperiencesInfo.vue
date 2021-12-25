<template>
	<div class="experiences-info-wrapper">
		<div class="row">
			<p class="fs-1 ms-4 me-4 text-capitalize text-center">
				Work Experience
			</p>
			<hr style="width: 97.5%!important; margin: auto;" />
			<template v-for="experience in experiences">
				<div :key="experience.company" class="experience ms-3 mt-3">
					<div class="company me-4 pull-right">
						<p class="fs-5 fw-bold">
							{{ experience.company }}
						</p>
					</div>
					<div
						class="position ms-2"
						v-for="role in experience.roles"
						:key="role.role"
					>
						<p class="fs-6 fw-bold" style="font-weight: 350">
							{{ role.role }} ({{ role.timeframe.from }} -
							{{ role.timeframe.to }})
						</p>

						<div v-if="role.responsibility">
							<ul>
								<li
									class="fs-6"
									v-for="resp in role.responsibility"
									:key="resp"
								>
									<p>{{ resp }}</p>
								</li>
							</ul>
						</div>
						<div class="project-wrapper" v-if="role.projects">
							<div
								class="project"
								v-for="project in role.projects"
								:key="project.name"
							>
								<p class="fs-6 fst-italic text-decoration-underline">
									{{ project.name }}
								</p>
								<ul>
									<li
										class="fs-6 responsibility"
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
				<hr
					:key="experience.company + 'hr'"
					style="width: 97.5%!important; margin: auto;"
				/>
			</template>
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
