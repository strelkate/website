<template>
	<div class="sorting">
		<div class="sorting__top">
			<div class="sorting__wrapper">
				<div class="sorting__subtitle">Сортировать по:</div>
				<div class="sorting__list">
					<div
						class="sorting__item"
						@click="onItemChangeClick('popular')"
						:class="sort==='popular'? 'sorting__item--active' : ''"
					>популярности
					</div>
					<div
						class="sorting__item"
						@click="onItemChangeClick('cheap')"
						:class="sort==='cheap'? 'sorting__item--active' : ''"
					>сначала дешевые
					</div>
					<div
						class="sorting__item"
						@click="onItemChangeClick('expensive')"
						:class="sort==='expensive'? 'sorting__item--active' : ''"
					>сначала дорогие
					</div>
				</div>
			</div>
			<div>
				<span class="sorting__subtitle">показывать по</span>
				<select class="sorting__select">
					<option>24</option>
					<option>36</option>
					<option>48</option>
				</select>
			</div>
		</div>
		<div class="sorting__labels">
			<div class="sorting__label" v-for="label in 4">Уточнение</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "Sorting",
	data() {
		return {
			sort: 'popular'
		}
	},
	methods: {
		onItemChangeClick(sort) {
			this.sort = sort;
		}
	}

}
</script>

<style lang="scss">
.sorting {
	width: 100%;
	margin-bottom: 20px;

	&__top {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-bottom: 12px;
	}

	&__wrapper {
		display: flex;
		align-items: center;
	}

	&__subtitle {
		font-family: OpenSans, sans-serif;
		line-height: 19px;
		margin-right: 15px;
	}

	&__list {
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: 365px;
	}

	&__item {
		font-family: OpenSans, sans-serif;
		line-height: 19px;
		margin-right: 10px;
		color: $color-link;
		cursor: pointer;

		&:last-child {
			margin-right: 0;
		}

		&:hover {
			color: $color-text;
		}

		&--active {
			color: $color-text;
			text-decoration: underline $color-primary;
		}
	}

	&__select {
		outline: none;
		padding: 6px 3px 8px 10px;
	}

	&__label {
		width: 100px;
		padding: 7px 15px;
		background-color: $color-filters;
		border-radius: 3px;
		border: 1px solid $color-filters;
		margin-right: 10px;
		cursor: pointer;
		&:hover {
			border: 1px solid $color-primary;
		}
	}

	&__labels {
		display: flex;
	}
}
</style>
