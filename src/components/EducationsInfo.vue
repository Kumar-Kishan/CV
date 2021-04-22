<template>
	<div class="educations-wrapper pt-2 pb-2">
		<div class="col-12 text-center fw-bold">
			Education
		</div>
		<div
			class="education"
			v-for="education in educations"
			:key="education.specialization"
		>
			<p class="fs-6 ms-4 pt-1">
				{{ education.specialization }}
			</p>
			<p class="fs-6 ms-4 fw-bold pt-1 pb-1">
				{{ education.college }}
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
