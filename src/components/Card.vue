<template>
	<div class="card">
		<div class="card__photo"></div>
		<div class="card__name">Наименование товара, которое не более 2 строк</div>
		<div class="card__prices">
			<div class="card__price card__price--new">ХХ ХХХ , $</div>
			<div class="card__price card__price--old">ХХ ХХХ $</div>
		</div>
		<button class="card__button">Кнопка</button>
	</div>
</template>

<script>
export default {
	name: "Card"
}
</script>

<style lang="scss">
.card {
	width: 260px;
	display: flex;
	flex-direction: column;

	&__photo {
		width: 100%;
		height: 260px;
		background-color: $color-background-photo;
		border-radius: 3px;
		margin-bottom: 10px;
	}

	&__name {
		margin-bottom: 23px;
		line-height: 18px;
	}

	&__prices {
		display: flex;
		align-items: center;
		margin-bottom: 15px;
	}

	&__price {
		font-family: OpenSans, sans-serif;
		line-height: 16px;

		&--new {
			font-weight: 700;
			margin-right: 16px;
			font-size: 16px;
		}

		&--old {
			font-size: 14px;
			color: #A9A9A9;
			text-decoration: line-through;
		}
	}
}
</style>
