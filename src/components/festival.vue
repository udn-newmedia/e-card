<template>
	<div class="festival">
		<img src="../assets/festival.png">
	</div>
</template>

<script>
export default {

  name: 'festival',

  data () {
    return {

    }
  }
}
</script>

<style lang="scss" scoped>
	$border: #D1AF00;
	.festival{
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: 91%;
		margin: 0 auto;
		img{
			width: 100%;
			height: auto;
		}
	}
	// .blessing{
	// 	width: 70%;
	// 	display: flex;
	// 	flex-direction: column;
	// 	justify-content: center;
	// 	align-items: center;
	// 	h2{
	// 		margin: 0;
	// 		color: #fff;
	// 		font-weight: normal;
	// 		letter-spacing: 5px;
	// 		line-height: 1;
	// 	}
	// 	h3{
	// 		color: $border;
	// 		margin-top: 5px;
	// 		display: flex;
	// 		justify-content: space-between;
	// 		align-items: center;
	// 	}
	// }
</style>