<template>
	<div class="icons">
		<swiper :options="swiperOption">
			<swiper-slide v-for="(page,index) of pages" :key='index'>
				<div class="icon"
					v-for='item of page'
					:key = 'item.id'
				>
					<div class="icon-img">
						<img class='icon-imgcontent' :src="item.imgUrl">
					</div>
					<p class='icon-dsec'>{{item.desc}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>	

<script>
	export default {
		name:'HomeIcons',
		props:{
			list:Array
		},
		data:function(){
			return {
				swiperOption : {
					autoplay:false
				}
			}
		},
		computed:{
			pages: function() {
				const pages = []
					this.list.forEach((item,index) =>{
						const page = Math.floor(index / 8)
							if(!pages[page]){
								pages[page] = []
							}
						pages[page].push(item)
					})
				return pages
			}
		},
    }
</script>

<style lang='stylus' scoped>
	@import '~styles/varibles.styl'
	@import '~styles/mixins.styl'
	.icons >>> .swiper-container
		height:0
		padding-bottom:50%
		.icon
			position:relative
			overflow:hidden
			float:left
			width:25%
			height:0
			padding-bottom:25%
		.icon-img 
			position:absolute
			top:0
			left:0
			bottom:.44rem
			right:0
			box-sizing:border-box
			padding:.1rem
		.icon-dsec 
			position:absolute
			right:0
			left:0
			bottom:0
			height:.44rem
			line-height:.44rem
			text-align:center
			color:$darkTextColor
			ellipsis()
		.icon-imgcontent
			display:block
			margin:0 auto
			height:100%
</style>