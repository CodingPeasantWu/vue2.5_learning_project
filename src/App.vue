<template>
  <div id="app">
    
   
    	<!-- 路由中的内容被加载过一次后，就把路由中的内容放到内存当中，下一次再进这个路由的时候，不需要你重新渲染这个组件，只需要你去内存中重新拿到这内容就可以了 -->
     <keep-alive excluede='Detail'>	
    	<router-view/><!-- 显示的是当前路由地址所对应的内容 -->
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

</style>
