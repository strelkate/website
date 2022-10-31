<template>
	<div class="pagination">
		<span class="pagination__number pagination__number--inactive">2</span>
		<span class="pagination__number pagination__number--active">3</span>
		<span class="pagination__number pagination__number--active">...</span>
		<span class="pagination__number pagination__number--inactive">13</span>
		<svg class="pagination__arrow">
			<use xlink:href="../../public/sprite.svg#arrow"></use>
		</svg>
	</div>
</template>

<script>
export default {
	name: "Pagination"
}
</script>

<style lang="scss">
.pagination {
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: 127px;
	margin-bottom: 55px;

	&__number {
		font-size: 16px;
		line-height: 18px;
		cursor: pointer;

		&--inactive {
			opacity: 50%;
		}
	}

	&__arrow {
		cursor: pointer;
		padding: 5px;
		width: 20px;
		height: 20px;
	}
}
</style>
