<template>
	<div class="apricot">
		<img src="../assets/apricot.png">
		<img src="../assets/apricot.png">
		<img src="../assets/apricot.png">
		<img src="../assets/apricot.png">
		<!-- <img class="udnLogo" src="../assets/udn-logo_black.png" alt='聯合報' title='聯合報'> -->
	</div>
</template>

<script>
export default {

  name: 'apricot',

  data () {
    return {

    }
  }
}
</script>

<style lang="scss" scoped>
	.apricot{
		position: absolute;
		z-index: 0;
		top: 0;
		left: 0;
		height: 100%;
		width: 100%;
		img{
			display: block;
			position: absolute;
			width: 73px;
			height: 73px;					
			z-index: 0;
			&:nth-child(1){
				top: 0;
				left: 0;
			}
			&:nth-child(2){
				top: 0;
				right: 0;
				transform: rotate(90deg);				
			}
			&:nth-child(3){
				bottom: 0;
				left: 0;
				transform: rotate(270deg);				
			}
			&:nth-child(4){
				bottom: 0;
				right: 0;
				transform: rotate(180deg);				
			}
		}
		.udnLogo{
			display: block;
			width: 128px;
			height: 25px;
			margin-left: -64px;
			left: 50%;
			bottom: 25px;
		}		
	}
	@media screen and (max-width: 767px) {

	}
	@media screen and (min-width: 768px) and (max-width: 1023px) {
		.apricot{
			img{
				width: 87px;
				height: 87px;						
			}
		}
	}
	@media screen and (min-width: 1024px){
		.apricot{
			img{
				width: 100px;
				height: 100px;						
			}
		}
	}		
</style>