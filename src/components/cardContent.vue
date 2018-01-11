<template>
	<div class="cardContent">
		<img class="contentBorderTop" src="../assets/contentBorderTop.png">
		<div class='mainContent'>
			<hr style='top: 0; left: 0;'>
			<hr style="top: 0; right: 0;">
			<hr style='bottom: 0; left: 0; width: 35%;'>
			<hr style="bottom: 0; right: 0; width: 35%;">
			<article class="blessContent">
				<p>親愛的夥伴</p>
				<p><br/></p>
				<p>2017年能與您攜手同行</p>
				<p>是聯合報的榮幸</p>
				<p><br/></p>
				<p>正派是我們的信念</p>
				<p>努力讓台灣變得更好，</p>
				<p>是我們的承諾</p>
				<p><br/></p>
				<p>今年</p>
				<p>也一起來吧！</p>
				<p>正向改變，讓台灣更好</p>
				<p><br/></p>
				<p>新年快樂</p>
				<p>聯合報</p>
				<p><br/></p>
				<hr class="blessTop" style='top: 0; left: 0; width: 23%;'>
				<hr class="blessTop" style="top: 0; right: 0; width: 23%;">
				<hr class="blessBottom" style='bottom: 0; left: 0; width: 30%;'>
				<hr class="blessBottom" style="bottom: 0; right: 0; width: 30%;">				
				<div class="lineFans">
					<img src="../assets/linefan.png">
					<img src="../assets/linefan.png">
					<img src="../assets/linefan.png">
					<img src="../assets/linefan.png">					
				</div>						
			</article>
		</div>
		<img class="contentBorderBottom" src="../assets/contentBorderBottom.png">
	</div>	
</template>

<script>
export default {

  name: 'cardContent',

  data () {
    return {

    }
  }
}
</script>

<style lang="scss" scoped>
	.cardContent{
		position: relative;
		width: 90%;
		margin: 0 auto 80px auto;
		// padding: 0 5px;
	}
	.mainContent{
		position: relative;
		width: 100%;
		border-left: 1px solid #fff;
		border-right: 1px solid #fff;
		padding: 8px 7px;
		hr{
			position: absolute;
			margin: 0;
			background: none;
			width: 28%;
			&:nth-child(1), &:nth-child(2){
				border-top: 1px solid #fff;
			}
			&:nth-child(3), &:nth-child(4){
				border-bottom: 1px solid #fff;
			}				
		}
	}
	.contentBorderTop{
		display: block;
		width: 50%;
		height: auto;
		margin: 0 auto;
	}
	.contentBorderBottom{
		position: relative;
		display: block;
		width: 35%;
		height: auto;
		margin: 0 auto;
		top: -5px;
	}
	.blessContent{
		position: relative;
		z-index: 1;
		width: 100%;
		border-left: 2px solid #D1AF00;
		border-right: 2px solid #D1AF00;
		padding: 10px 0;
		.blessTop{
			border-top: 2px solid #D1AF00;	
		}
		.blessBottom{
			border-bottom: 2px solid #D1AF00;
		}
		p{
			position: relative;
			z-index: 10;
			width: 100%;
			color: #fff;
			text-align: center;
		}
	}
	.lineFans{
		position: absolute;
		z-index: 0;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		img{
			position: absolute;
			z-index: auto;
			width: 40px;
			height: 40px;
			&:nth-child(1){
				top: 0;
				left: 0;
				margin-top: 5px;
				margin-left: 5px;
			}
			&:nth-child(2){
				top: 0;
				right: 0;
				margin-top: 5px;
				margin-right: 5px;
				transform: rotateY(180deg);
			}			
			&:nth-child(3){
				bottom: 0;
				left: 0;
				margin-bottom: 5px;
				margin-left: 5px;
				transform: rotatez(-90deg);
			}	
			&:nth-child(4){
				bottom: 0;
				right: 0;
				margin-bottom: 5px;
				margin-right: 5px;
				transform: rotatez(180deg);
			}					
		}
	}
	@media screen and (max-width: 767px) {

	}
	@media screen and (min-width: 768px) and (max-width: 1024px) {
		.cardContent{
			width: 80%;
		}
	}
	@media screen and (min-width: 1024px){
		.cardContent{
			width: 60%;
		}
		.lineFans{
			img{
				width: 60px;
				height: 60px;
			}
		}
		.blessContent{
			border-left: 3px solid #D1AF00;
			border-right: 3px solid #D1AF00;
			.blessTop{
				border-top: 3px solid #D1AF00;	
			}
			.blessBottom{
				border-bottom: 3px solid #D1AF00;
			}
		}
		.mainContent{
			border-left: 2px solid #fff;
			border-right: 2px solid #fff;
			hr{
				&:nth-child(1), &:nth-child(2){
					border-top: 2px solid #fff;
				}
				&:nth-child(3), &:nth-child(4){
					border-bottom: 2px solid #fff;
				}				
			}
		}			
	}		
</style>