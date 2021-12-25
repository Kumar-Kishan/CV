<template>
	<div class="educations-wrapper">
		<div class="fs-1 col-12 ms-4 mb-0 text-center">
			Education
		</div>
		<hr style="margin-top: 0; margin-bottom: 0;" />
		<div
			class="education"
			v-for="education in educations"
			:key="education.specialization"
		>
			<p class="fs-6 ms-4 pt-1">
				{{ education.specialization }} ({{ education.timeframe.from }} -
				{{ education.timeframe.to }})
			</p>
			<p class="fs-6 ms-4 fw-bold pt-1 pb-1">
				{{ education.college }} ({{ education.university }})
			</p>
		</div>
	</div>
</template>

<script>
export default {
	name: "EducationsInfo",
	props: {
		educations: Array
	}
};
</script>

<style></style>
