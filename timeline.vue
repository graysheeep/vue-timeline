<template>
	<div class="vux-timeline">
		<ul>
			<slot></slot>
		</ul>
	</div>
</template>

<style lang="less">
	.vux-timeline {
		background-color:#EEE;
		padding:1rem;

		ul li {
			list-style: none;
		}

	}
</style>

<script>
	import TimelineItem from './timeline-item'

	export default {
	  components: {
	    TimelineItem
	  },
	  ready () {
        this.setChildProps()
      },
	  methods: {
	    setChildProps () {
	      const len = this.$children.length
	      this.$children.forEach((child, index) => {
	        child.isLast = index === len - 1
	        child.isFirst = index === 0
	      })
	    }
	  }
	}
</script>