<template>
	<div class="wuyear">
		<img class="wings" src="../assets/wings.png">
		<img class="centerWord" src="../assets/year.png">
		<img class="wings" style="transform: rotateY(180deg)" src="../assets/wings.png">
	</div>	
</template>

<script>
export default {

  name: 'wuyear',

  data () {
    return {

    }
  }
}
</script>

<style lang="scss" scoped>
	.wuyear{
		margin: 10px auto;
		height: 70px;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.wings{
		height: 28px;
		width: 35%;
	}
	.centerWord{
		width: 17%;
		height: auto;
	}
	@media screen and (min-width: 768px) and (max-width: 1023px) {
		.centerWord{
			width: 18%;
			height: auto;
		}
	}
	@media screen and (min-width: 1024px){
		.centerWord{
			width: 15%;
			height: auto;
		}
	}		
</style>