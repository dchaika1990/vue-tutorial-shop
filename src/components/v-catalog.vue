<template>
	<div class="v-catalog grid-cols-3 gap-40">
		<v-catalog-item
			v-for="product in PRODUCTS"
			:key="product.article"
			:product="product"
			@sendArticle="showChildArticleInConsole"
		/>
	</div>
</template>

<script>
import vCatalogItem from './v-catalog-item'
import {mapActions, mapGetters} from 'vuex'

export default {
	name: "v-catalog",
	data: () => ({

	}),
	computed: {
		...mapGetters(['PRODUCTS'])
	},
	methods: {
		...mapActions(['GET_PRODUCTS_FROM_API']),
		showChildArticleInConsole(article) {
			console.log(article)
		},

	},
	mounted() {
		this.GET_PRODUCTS_FROM_API()
			.then((res) => {
				if (res.data){
					console.log('Data arrived')
				}
			})
	},
	components: {
		vCatalogItem
	}
}
</script>

<style scoped>

</style>