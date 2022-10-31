<template>
	<div class="price">
		<h4 class="price__subtitle">Цена, валюта</h4>
		<div class="price__top">
			<span class="price__span">от</span>
			<input type="number" class="price__input" v-model="minPrice">
			<span class="price__span">до</span>
			<input type="number" class="price__input" v-model="maxPrice">
			<span class="price__span">P</span>
		</div>
		<section class="range-slider">
			<span class="rangeValues"></span>
			<input type="range" class="side-filters__range" v-model="minPrice" min="1000" max="1000000">
			<input type="range" class="side-filters__range" v-model="maxPrice" min="1000" max="1000000">
		</section>
	</div>
</template>

<script>
export default {
	name: "Price",
	data() {
		return {
			minPrice: 1000,
			maxPrice: 1000000
		}
	}
}
</script>

<style lang="scss">
.price {
	&__subtitle {
		margin: 0 0 16px 0;
	}

	&__top {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	&__input {
		width: 110px;
		margin: 0 9px;
	}

	&__span {
		font-size: 12px;
		opacity: 50%;
	}
}

@mixin range-slider() {
	position: relative;
	width: 100%;
	height: 14px;
	float: left;
	text-align: center;

	input[type="range"] {
		width: 100%;
		position: absolute;
		overflow: hidden;
		left: 0;
		top: 14px;
		outline: none;
		background-color: black;
		margin: 0;
		padding: 0;
		height: 14px;
		border-right: 30px;
		-webkit-appearance: none;
	}

	input[type="range"]::-webkit-slider-thumb {
		pointer-events: all;
		position: relative;
		z-index: 1;
		outline: 0;
		-webkit-appearance: none;
		background-color: #FFFFFF;
		width: 14px;
		height: 14px;
		border: 2px solid #000000;
		border-radius: 50%;
	}
}

.range-slider {
	@include range-slider();
}
</style>
