<script>
  let scrollY
  $: console.log(scrollY)
  let time
  let duration
  $: {
	const totalScroll = document.documentElement.scrollHeight - window.innerHeight
    time = duration * (scrollY / totalScroll)
  }
</script>

<svelte:window bind:scrollY />



<div class="scroll-container" />




<div class="video-container">
	<video
	bind:currentTime="{time}"
	bind:duration
	preload="metadata"
	muted
	src="video/Tomas-Fisk-crossing.mp4"
	type="video/mp4"
  
  />


</div>



<style>
	
	.scroll-container {
	  height: 5000px;
	}
  
	.video-container {
	  position: absolute;
	  top: 0;
	  bottom: 0;
	  overflow: hidden;
	}
  
	.video-container video {
	  min-width: 100%;
	  min-height: 100%;
	  width: auto;
	  height: auto;
	  position: fixed;
	  top: 50%;
	  left: 50%;
	  transform: translate(-50%, -50%);
	}
  
  
  </style>