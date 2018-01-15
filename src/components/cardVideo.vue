<template>
	<div class="videoContainer">
		<video playsinline webkit-playsinline="true"
		  	   poster="../assets/meta.jpg"
		  	   @timeupdate.slef="handle_playing"
		  	   @click.slef="handle_click"
		  	   @playing.slef="handle_playing">
		  <source
		    src="../assets/video.mp4"
		    type="video/mp4">
		  Your browser doesn't support HTML5 video tag.
		</video>				
	</div>
</template>

<script>
import Utils from 'udn-newmedia-utils';
import _throttle from 'lodash.throttle';

export default {

  name: 'cardVideo',
  data () {
    return {

    }
  },
  methods: {
  	handle_playing: _throttle(function() {
  		const tv = this.$el.children[0]
  		const toSend = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
  		let timePercent = Math.floor(tv.currentTime / tv.duration * 100)
  		if (timePercent === 10 ||
  			timePercent === 20 ||
  			timePercent === 30 ||
  			timePercent === 40 ||
  			timePercent === 50 ||
  			timePercent === 60 ||
  			timePercent === 70 ||
  			timePercent === 80 ||
  			timePercent === 90 ||
  			timePercent === 100) {
  			this.handle_gaSend(timePercent)
  		}
  	}, 1000),
  	handle_click: function() {
  		const thisVideo = this.$el.children[0]
  		if (thisVideo.paused) {
  			thisVideo.play();
	        ga("send", {
	            "hitType": "event",
	            "eventCategory": "Video",
	            "eventAction": "Video",
	            "eventLabel": "[" + Utils.detectPlatform() + "] [" + document.querySelector('title').innerHTML + "] [影片播放]"
	        });  			
  		} else {
  			thisVideo.pause();
	        ga("send", {
	            "hitType": "event",
	            "eventCategory": "Video",
	            "eventAction": "Video",
	            "eventLabel": "[" + Utils.detectPlatform() + "] [" + document.querySelector('title').innerHTML + "] [影片暫停]"
	        }); 
  		}
  	},
  	handle_playing: function() {
  		const tv = this.$el.children[0]
  		tv.controls = true;
  	},
  	handle_gaSend: function (timePercent) {
        ga("send", {
            "hitType": "event",
            "eventCategory": "Video",
            "eventAction": "Video",
            "eventLabel": "[" + Utils.detectPlatform() + "] [" + document.querySelector('title').innerHTML + "] [影片觀看"+ timePercent + "%]"
        });
  	}
  }
}
</script>

<style lang="scss" scoped>
	.videoContainer{
		display: flex;
		align-items: center;
		justify-content: center;
	}
	video{
		display: block;
		width: 100%;
		height: auto;
		cursor: pointer;
	}
</style>