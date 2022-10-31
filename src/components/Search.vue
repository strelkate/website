<template>
	<div class="search">
		<div class="search__top">
			<div class="search__bar">
				<div class="search__symbols">
					<svg class="search__icon search__icon--glass">
						<use xlink:href="../../public/sprite.svg#search"></use>
					</svg>
					<div class="search__line"></div>
				</div>
				<div class="search__request">
					<input type="text" class="search__input" placeholder="Запрос пользователя" v-model="request">
					<svg class="search__icon search__icon--close" @click="onRequestClearClick">
						<use xlink:href="../../public/sprite.svg#close"></use>
					</svg>
				</div>
				<button class="search__button">Найти</button>
			</div>
			<button class="search__button--close" >Закрыть</button>
		</div>
		<div class="search__result">
			<h2 class="search__title">Результаты по запросу</h2>
			<span class="search__span">
				Показаны результаты для “Запрос пользозвателя”. Вы искали “<i>Зопрос</i> пользователя”.
			</span>
		</div>
	</div>
</template>

<script>
export default {
	name: "Search",
	data() {
		return {
			request: ''
		}
	},
	methods: {
		onRequestClearClick() {
			this.request = ''
		}
	}
}
</script>

<style lang="scss">
.search {
	width: 100%;

	&__top {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-bottom: 31px;
	}

	&__bar {
		width: 100%;
		position: relative;
		max-width: 930px;
		display: flex;
		align-items: center;
	}

	&__request {
		width: 100%;
	}

	&__input {
		width: 100%;
		padding: 11px 57px;
		border-radius: 3px 0 0 3px;
	}

	&__symbols {
		display: flex;
		align-items: center;
		position: absolute;
		left: 16px;
	}

	&__icon {
		&--glass {
			width: 17px;
			height: 17px;
		}

		&--close {
			position: absolute;
			width: 20px;
			height: 20px;
			top: 9px;
			right: 10px;
			cursor: pointer;
			padding: 5px;
		}
	}

	&__line {
		width: 1px;
		height: 16px;
		background-color: $color-text;
		margin-left: 12px;
	}

	&__button {
		width: 146px;
		position: absolute;
		right: -145px;
		border-radius: 0 3px 3px 0;

		&--close {
			width: 117px;
			background-color: $color-background;
			border: 1px solid #DEDEDE;

			&:hover {
				background-color: $color-filters;
			}
		}
	}

	&__result {
		display: flex;
		align-items: center;
		margin-bottom: 26px;
	}

	&__title {
		margin: 0 36px 0 0;
		font-size: 28px;
		font-weight: 400;
		line-height: 32px;
	}

	&__span {
		font-family: OpenSans, sans-serif;
		line-height: 19px;
		color: $color-text-inactive;
	}
}
</style>
