<template>
	<div class="header">
		<h2 class="header__title">Шапка сайта</h2>
	</div>
</template>

<script>
export default {
	name: "Header"
}
</script>

<style lang="scss">
.header {
	background-color: $color-text;
	padding: 43px 24px 41px 24px;
	margin-bottom: 32px;

	&__title {
		color: white;
		font-size: 14px;
		margin: 0;
		line-height: 16px;
	}
}
</style>
