<template>
	<div class="window_page col">
		<div class="head" v-if="$route.meta.showHead">
			<comHead></comHead>
		</div>
		<div class="container row">
			<div class="menu_wrap"  v-if="$route.meta.showMenu">
				<menuList></menuList>
			</div>
			<div class="page_con">
				<router-view></router-view>
			</div>
			
		</div>
		
	</div>
</template>
<script setup lang="ts">
import { ref, reactive, getCurrentInstance, onMounted, onActivated, nextTick,computed,watch } from 'vue';
import comHead from './components/comHead.vue';
import menuList from './components/menuList.vue';
</script>

<style scoped lang="scss">
.window_page{
	align-items: flex-start;
	height: 100vh;
	.head{
		width: 100vw;
	}
	.container{
		align-items: flex-start;
		flex: 1;
		width: 100%;
		.menu_wrap{
			height: 100%;
		}
		.page_con{
			flex: 1;
			padding: 20px;
			overflow-y: scroll;
			height:calc(100vh - 150px);
		}
	}
}
</style>