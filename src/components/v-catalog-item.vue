<template>
	<div class="v-catalog-item cart">
		<div class="cart-media">
			<img :src="require('../assets/images/' + product.image)" alt="">
		</div>
		<div class="cart-content">
			<h4>{{ product.name }}</h4>
			<p>Price: {{ product.price }} P</p>
			<button
				class="btn btn-maincolor"
				@click="sendDataToParent"
			>Add to cart
			</button>
		</div>
	</div>
</template>

<script>
export default {
	name: "v-catalog-item",
	props: {
		product: {
			type: Object,
			required: true,
			default() {
				return {}
			}
		}
	},
	methods: {
		sendDataToParent() {
			this.$emit('sendArticle', this.product.article)
		}
	}
}
</script>

<style scoped>

</style>