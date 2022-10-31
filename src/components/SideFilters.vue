<template>
	<div class="side-filters">
		<div>Все категории</div>
		<div class="side-filters__categories">
			<div class="side-filters__category" v-for="(_, index) in 8">
				Категория в которой нашли что-то <span class="side-filters__last-word">(ххх)</span>
			</div>
		</div>
		<span class="side-filters__category-more">Ещё 10 категорий...</span>
		<Price/>
		<div class="side-filters__wrapper">
			<h4 class="side-filters__subtitle">Бренды</h4>
			<div class="side-filters__clear" @click="onBrandsClearClick">Очистить</div>
		</div>
		<div class="side-filters__brand">
			<input class="side-filters__checkbox" type="checkbox" id="brand_1" value="brand_1" v-model="checkedNames">
			<label for="brand_1">Бренд<span class="side-filters__last-word"> (xxx)</span></label>
		</div>
		<div class="side-filters__brand">
			<input class="side-filters__checkbox" type="checkbox" id="brand_2" value="brand_2" v-model="checkedNames">
			<label for="brand_2">Бренд<span class="side-filters__last-word"> (x)</span></label>
		</div>
		<div class="side-filters__brand">
			<input class="side-filters__checkbox" type="checkbox" id="brand_3" value="brand_3" v-model="checkedNames">
			<label for="brand_3">Бренд<span class="side-filters__last-word"> (x xxx)</span></label>
		</div>
	</div>
</template>

<script>
import Price from "@/components/Price";

export default {
	name: "SideFilters",
	components: {Price},
	data() {
		return {
			checkedNames: []
		}
	},
	methods: {
		onBrandsClearClick() {
			this.checkedNames = []
		}
	}
}
</script>

<style lang="scss">
.side-filters {
	display: flex;
	flex-direction: column;
	width: 290px;
	margin-top: 9px;

	&__categories {
		margin-top: 14px;
	}

	&__category {
		color: $color-link;
		margin-bottom: 14px;
		cursor: pointer;

		&:hover {
			text-decoration: underline;
		}
	}

	&__last-word {
		font-size: 12px;
		color: #ABABAB;
	}

	&__category-more {
		color: $color-link;
		cursor: pointer;
		margin-bottom: 46px;
	}

	&__wrapper {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin: 40px 0 14px 0;
	}

	&__subtitle {
		margin: 0;
	}

	&__clear {
		font-size: 10px;
		line-height: 11px;
		color: #333333;
		text-decoration: underline;
		cursor: pointer;
		opacity: 50%;
	}

	&__brand {
		display: flex;
		align-items: center;
		margin-bottom: 15px;
	}

	&__checkbox {
		margin: 0 10px 0 0;
	}

}
</style>
