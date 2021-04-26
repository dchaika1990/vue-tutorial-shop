<template>
	<div class="v-main-wrapper grid-container">
		<p>{{title}}</p>
		<v-catalog />
		<v-cart />
	</div>
</template>

<script>
import vCatalog from './v-catalog'
import vCart from './v-cart'

export default {
	name: "v-main-wrapper",
	data: () => ({
		title: 'Main wrapper'
	}),
	components: {
		vCatalog, vCart
	}
}
</script>

<style scoped>

</style>