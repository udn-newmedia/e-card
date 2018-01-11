<template>
	<div class="outBorderWrapper">
		<div class="outBorderH" style="top: 0;"></div>
		<div class="outBorderH" style="bottom: 0;"></div>
		<div class="outBorderV" style="left: 0;"></div>
		<div class="outBorderV" style="right: 0;"></div>		
	</div>
</template>

<script>
export default {

  name: 'outBorder',

  data () {
    return {

    }
  }
}
</script>

<style lang="scss" scoped>
	.outBorderWrapper{
		position: absolute;
		z-index: 0;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
	}
	.outBorderH{
		position: absolute;
		left: 0;
		height: 5px;
		width: 100%;
		// background-color: #fff;
		background: url('../assets/outBorderH_Mob.png') repeat;
		background-size: 100% 15px;	
	}
	.outBorderV{
		position: absolute;
		top: 0;
		height: 100%;
		width: 5px;
		// background-color: #fff;
		background: url('../assets/outBorderV.png') repeat;
		background-size: 15px 100px;	
	}
	@media screen and (min-width: 1024px) {
		.outBorderH{
			background: url('../assets/outBorderH_PC.png') no-repeat center;
		}
	}	
</style>