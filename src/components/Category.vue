<template>
	<div class="category" :class="blurClass">
		<div class="category__image"></div>
		<div class="category__text">
			<div class="category__name">Название категории</div>
			<div class="category__count">134 товара</div>
		</div>
		<div class="category__line" v-if="!blurClass"></div>
	</div>
</template>

<script>
export default {
	name: "Category",
	props: {
		blur: {
			type: Boolean,
			default: false,
		}
	},
	computed: {
		blurClass() {
			return this.blur ? 'category__blur' : ''

		}
	}
}
</script>

<style lang="scss">
.category {
	display: flex;
	align-items: center;
	width: 231px;
	justify-content: space-between;
	position: relative;
	cursor: pointer;

	&__image {
		width: 60px;
		height: 60px;
		background-color: $color-background-photo;
		border-radius: 3px;
	}

	&__text {
		display: flex;
		flex-direction: column;
		font-family: OpenSans, sans-serif;
		white-space: nowrap;
		text-overflow: clip;
		width: 125px;
	}

	&__name {
		color: #333333;
		line-height: 19px;
		margin-bottom: 9px;
	}

	&__count {
		font-size: 12px;
		line-height: 16px;
		color: $color-text-inactive;
	}

	&__line {
		width: 1px;
		height: 60px;
		background-color: $color-line;
		margin-left: 20px;
	}

	&__blur {
		width: 195px;
		&:after {
			content: '';
			position: absolute;
			top: 0;
			left: 68px;
			right: 0;
			bottom: 0;
			width: 143px;
			height: 60px;
			background: linear-gradient(269.76deg, #FFFFFF 62.83%, rgba(255, 255, 255, 0) 145.7%);
			//background: linear-gradient(269.76deg, #c91515 62.83%, rgba(255, 255, 255, 0) 145.7%);
		}
	}
}
</style>
