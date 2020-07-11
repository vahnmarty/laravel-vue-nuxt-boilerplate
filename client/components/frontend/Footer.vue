<template>
	<footer class="site-footer bg-dark py-5 sticky-footer">
		<div class="container">
			<p class="text-center text-white mb-0">All rights reserved {{ year }} <span class="mx-5">|</span> Compiled by {{ author }}</p>
		</div>
	</footer>
</template>
<style>
	.sticky-footer{
		position: absolute;
		bottom: 0;
		width: 100%;
	}
</style>
<script>
	export default{

		data: () => ({
			year: '2020',
			author: 'Mr-Robot'
		})
	}
</script>