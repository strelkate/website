<template>
	<div class="main-content">
		<Sorting/>
		<div class="main-content__cards">
			<Card class="main-content__card" v-for="(_, index) in 9" :key="index"/>
		</div>
		<Pagination/>
	</div>
</template>

<script>
import Sorting from "@/components/Sorting";
import Card from "@/components/Card";
import Pagination from "@/components/Pagination";

export default {
	name: "MainContent",
	components: {Pagination, Card, Sorting},

}
</script>

<style lang="scss">
.main-content {
	width: 100%;
	&__cards {
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
	}
	&__card {
		margin-bottom: 40px;
	}
}
</style>
