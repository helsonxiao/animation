<template>
	<view class="content">
		<uni-icons :type="iconType" size="30" @click="switchStar"></uni-icons>
    <view :class="starClass" @click="star"></view>
    <!-- <view class="heart"></view> -->
	</view>
</template>

<script>
  import { uniIcons } from '@dcloudio/uni-ui';
	export default {
    components: {
      uniIcons,
    },
		data() {
			return {
				iconType: 'star',
        starClass: 'fave',
			}
		},
		onLoad() {

		},
		methods: {
      switchStar() {
        if (this.iconType === 'star') {
          this.iconType = 'star-filled';
          return;
        }
        this.iconType = 'star';
      },
      star() {
        this.starClass += " active";
      }
		},
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

  .fave {
    background: url(../../static/twitter_fave.png) no-repeat;
    background-position: 0 0;
    width: 70px;
    height: 50px;
    cursor: pointer;
  }
  .fave.active {
    background-position: -3519px 0;
    transition: background 0.8s steps(55);
    /* transition: background 0.8s linear; */
  }
  
  .heart {
    width: 100px;
    height: 100px;
    background: url(https://cssanimation.rocks/images/posts/steps/heart.png) no-repeat;
    background-position: 0 0;
    animation: fave-heart 2s steps(28) infinite;
    cursor: pointer;
  }
  .heart:hover {
    background-position: -2800px 0;
    transition: background 1s steps(28);
  }
  @keyframes fave-heart {
    0% {
      background-position: -2800px 0;
    }
    50% {
      background-position: 0 0;
    }
    100% {
      background-position: -2800px 0;
    }
  }
</style>
