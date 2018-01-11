<template>
	<div class="cardSideDec hidden-xs hidden-sm" :style="{height: cardSideHeight + 'px'}">
		<img class="square" src="../assets/square.png">
		<img src="../assets/fan.png">
		<img class="square" src="../assets/square.png">
	</div>
</template>

<script>
export default {

  name: 'cardSideDec',

  data () {
    return {
    	cardSideHeight: 0,
    }
  },
  methods:{
  	handle_height: function () {
  		const target = document.getElementsByClassName('videoSection')[0]
  		this.cardSideHeight = target.clientHeight
  	}
  },
  mounted() {
  	this.handle_height()
  }
}
</script>

<style lang="scss" scoped>
	.cardSideDec{
		display: flex;
		flex-direction: column;
		width: 15%;
		justify-content: space-around;
		align-items: center;
		img{
			display: block;
			width: 50px;
			height: auto;
			&:nth-child(1){
				transform: rotate(90deg);
			}
			&:nth-child(3){
				transform: rotate(-90deg);
			}
		}
	}
</style>