<template>
	<div class="app">
		<Header/>
		<div class="container">
			<Search/>
			<div class="app__categories">
				<Category v-for="(_, index) in 5" :key="index" :blur="index===5-1"/>
			</div>
			<div class="app__main-content">
				<SideFilters class="app__side-filters"/>
				<MainContent/>
			</div>
		</div>
	</div>
</template>

<script>
import Header from './components/Header.vue'
import Search from "@/components/Search";
import Category from "@/components/Category";
import SideFilters from "@/components/SideFilters";
import MainContent from "@/components/MainContent";

export default {
	name: 'App',
	components: {
		MainContent,
		SideFilters,
		Category,
		Header, Search
	},
}
</script>

<style lang="scss">
.app {
	&__main-content {
		width: 100%;
		display: flex;
	}

	&__categories {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-bottom: 30px;
	}

	&__side-filters {
		margin-right: 42px;
	}
}
</style>
