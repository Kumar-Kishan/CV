<template>
	<div class="educations-wrapper">
		<div class="col-12 text-center fw-bold">
			Educations
		</div>
		<div
			class="education"
			v-for="education in educations"
			:key="education.specialization"
		>
			<p class="fs-6 ms-4">
				{{ education.specialization }}
			</p>
			<p class="fs-6 ms-4 fw-bold">
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
