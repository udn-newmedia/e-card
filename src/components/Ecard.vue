<template>
	<section class="container ecard-wrapper">
		<OutBorder />
		<div class="goldBorder">
			<div class="cardMain">
				<Apricot />
				<div class="cardHead">
					<div class="chun">
						<img src="../assets/square.png">
						<img src="../assets/chun.png" style="height: 100%; width: auto;">
						<img src="../assets/square.png" style="transform: rotateY(180deg)">
					</div>					
					<img class="dogyear" src="../assets/2018Dog.png">
					<Wuyear />
					<Festival />
				</div>
				<div class="videoSection">
					<CardSideDec />
					<div class="videoBorder">					
						<CardVideo />		
					</div>
					<CardSideDec />
				</div>
				<Share class="customShare" href='https://udn-newmedia.github.io/e-card/dist/'/>
				<div class="contentSection">
					<CardSideDec style="transform: rotate(180deg);"/>
					<CardContent />
					<CardSideDec style="transform: rotate(180deg);"/>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
import Apricot from '../components/apricot.vue';
import CardSideDec from '../components/cardSideDec.vue';
import CardContent from '../components/cardContent.vue';
import CardVideo from '../components/cardVideo.vue';
import Festival from '../components/festival.vue';
import OutBorder from '../components/outBorder.vue';
import Share from '../components/Share.vue';
import Wuyear from '../components/wuyear.vue';

export default {

  name: 'Ecard',
  components: {
    OutBorder,
    Apricot,
    Wuyear,
    Festival,
    Share,
    CardContent,
    CardSideDec,
    CardVideo
  },
  data () {
    return {

    }
  }
}
</script>

<style lang="scss" scoped>
	$main: #C1272E;
	$border: #D1AF00;
	.ecard-wrapper{
		position: relative;
		padding: 5px;
		background-color: $main;
		border: 1px solid $border;
	    &::before, &::after{
			content: none;
	    }
	}

	.goldBorder{
		border: 1px solid $border;
		width: 100%;
		height: 100%;
		padding: 5px;
	}
	.cardMain{
		position: relative;
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		padding: 0 5px;
		div{
			z-index: 1;
		}
	}
	.chun{
		margin: 5px auto 15px auto;
		width: 160px;
		height: 60px;
		display: flex;
		align-items: center;
		justify-content: space-around;
		img{
			height: auto;
			&:nth-child(1), &:nth-child(3){
				width: 20%;
			}
			&:nth-child(2){
				width: 50%;
			}
		}
	}
	.cardHead{
		margin: 0 auto;
		width: 100%;
		padding: 0 30px;
	}
	.dogyear{
		width: 100%;
		height: auto;
	}
	.videoSection{
		width: 100%;
		margin: 0 auto;
		display: flex;
		justify-content: space-around;
		align-items: center;
		z-index: 999 !important;
	}
	.videoBorder{
		margin: 5px auto 0 auto;
		z-index: 1000;
		width: 100%;
		height: auto;
		padding: 15px;
		background: transparent url('../assets/videoBorder.png') left top no-repeat;
		background-size: 100% 100%;
	}	
	.contentSection{
		width: 100%;
		display: flex;
		align-items: center;
	}
	.customShare{
		margin: 10px auto;
		z-index: 999 !important;
	}
	@media screen and (max-width: 767px) {
		.container{
			width: 100%;
		}
	}
	@media screen and (min-width: 768px) and (max-width: 1023px) {
		.cardHead{
			width: 70%;
		}
		.videoBorder{
			padding: 20px;
		}		
	}
	@media screen and (min-width: 1024px){
		.cardHead{
			width: 55%;
		}
		.videoSection{
			width: 100%;
		}
		.videoBorder{
			padding: 25px;
			width: 70%;
		}			
		.goldBorder{
			padding: 9px;
		}		
	}	
</style>