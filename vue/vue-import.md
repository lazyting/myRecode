1，导入方法
	1.1，export 和 export default 区别

		先是 export 
		需要加花括号 可以一次导入多个也可以一次导入一个，但都要加括号
		import {getDataByReportNo,saveGarageData} from '@/api/garage'

		再是 export default 
		import fetch from '@/utils/fetch' //不需要加花括号 只能一个一个导入

	1.2，导入成组的方法
		import * as tools from './libs/tools'
		其中tools.js中有多个export方法,把tools里所有export的方法导入
		直接用 this.$tools.method调用就可以了


2，导入css
	import 'swiper/dist/css/swiper.css'

	如果是在.vue文件中那么在外面套个style
	<style>
	 @import './test.css'; 
	 
	</style>

3，导入组件
	import { swiper, swiperSlide } from 'vue-awesome-swiper'
	export default {
	  components: {
	    swiper,
	    swiperSlide,
	  }