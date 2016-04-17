<template>
	<div class="vux-timeline">
		<div class="start-point">
			<div class="date">2016-04-15</div>
			<div class="point"></div>
			<!-- <div>456</div> -->
		</div>
		<div
			v-for="i in total-1"
			:class=" {'content-point':points[i],'blank-point':!points[i]} ">
				<div class="point"></div>
		</div>
	</div>
</template>

<style lang="less">
	.vux-timeline {
		display:-webkit-box;
		background-color:#EEE;
		padding:1rem;


		.blank-point,.content-point {
			width:100%;
			position:relative;
			-webkit-box-flex:1;
			text-align:right;
		}

		.start-point {
			position:relative;
			.point {
				width:15px;
				height:15px;
				border-radius:99px;
				background-color:#009C23;
				position:absolute;
				right:0;top:50%;
				transform:translateY(-50%);
			}
		}
		
		.blank-point {
			.point {
				width:15px;
				height:15px;
				border-radius:99px;
				background-color:#CCC;
				position:absolute;
				right:0;top:50%;
				transform:translateY(-50%);
			}

			&::before {
				position:absolute;
				top:50%;
				left:0;
				content:'';
				height:2px;
				background-color:#CCC;
				width:98%;
			}
		}

		.content-point {
			.point {
				width:15px;
				height:15px;
				border-radius:99px;
				background-color:#009C23;
				position:absolute;
				right:0;top:50%;
				transform:translateY(-50%);
			}

			&::before {
				position:absolute;
				top:50%;
				left:0;
				content:'';
				height:2px;
				background-color:#009C23;
				width:98%;
			}
		}

		.icon {
			width:6px;
			height:6px;
			display:inline-block;
			background-color:#F37B00;
		}

		.date {
			font-size:0.6rem;
			color:#595959;
		}
	}
</style>

<script>
	export default {
	  data () {
	    return {
	      total: 3,
	      points: [true, false]
	    }
	  }
	}
</script>
