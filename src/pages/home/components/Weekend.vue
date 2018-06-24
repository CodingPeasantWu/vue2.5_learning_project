<template>
	<div class='title'>
		<div>周末去哪儿</div>
		<ul class="ul-item">
			<li class='item border-bottom' 
				v-for='item of list'
				:key='item.id'
				>
				<div class="item-img-wrapper">
					<img :src='item.imgUrl' class="item-img">
				</div>
				<div class='item-info'>
					<p class="item-title">{{item.title}}</p>
					<p class='item-desc'>{{item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		name:'HomeWeekend',
		props:{
			list:Array
		}
	}
</script>

<style lang='stylus' scoped>
@import'~styles/mixins.styl'
	.title
		line-height:.8rem
		background:#eee
		text-indent:.2rem
		margin-top:.2rem
	.ul-item
		background:#fff
	.item-img-wrapper
		overflow:hidden
		height:0
		padding-bottom:37.09%
		.item-img
			width:100%
			display:block
		.item-info
			padding:.1rem
			.item-title
				line-height:.54rem
				font-size:.32rem
				ellipsis()
			.item-desc
				line-height:.4rem
				color:#ccc
				ellipsis()
</style>