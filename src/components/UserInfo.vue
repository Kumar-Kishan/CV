<template>
	<div class="user-info-wrapper text-break text-wrap ms-2 me-2">
		<p class="text-center fw-bold fs-1">
			{{ name }}
		</p>
		<div class="pull-right">
			<p class="fs-6 pt-1">
				<i class="fa fa-envelope"></i>
				{{ contact.email }}
			</p>
			<p class="fs-6 pt-1 pb-1">
				<i class="fa fa-link"></i>
				{{ contact.website }}
			</p>
		</div>
		<div class="pull-left">
			<p class="pt-2 fs-6">
				<i class="fa fa-github"></i>
				{{ contact.github }}
			</p>
			<p class="fs-6 pt-1">
				<i class="fa fa-stack-overflow"></i>
				{{ contact.stackoverflow }}
			</p>
		</div>
	</div>
</template>

<script>
export default {
	name: "UserInfo",
	props: {
		name: String,
		contact: Object
	}
};
</script>

<style>
.user-info-wrapper {
	/* background: #00ff00; */
	height: 5em;
	padding-left: 0.3cm;
	margin-top: 0.25cm;
}
</style>
