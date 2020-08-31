<template>
	<div class="main">
		<ul id="star-box">
			<li v-for="(i,idx) in 5" :key="i">
				<span :style="{width:StarWidth(idx)}"></span>
			</li>
		</ul>
	</div>
</template>
<script>
	export default {
		props:{
			// score:Number,
			score:{
				type:Number,
				default:0
			}
		},
		data() {
			return {
				starArr:[],
			}
		},
		methods:{
			StarWidth(idx){
				
				// const w = this.starArr[idx] * 100
				//消除NaN
				const w = (this.starArr[idx] || 0) * 100
				console.log(w)
				return `${w}%`
			},
			initStar(){
				//利用進位把小數點消掉
				const Int = this.score | 0;
				//格式化小數點
				const Point = this.score.toFixed(1).split('.')[1];
				console.log(Point)
				for(let s = 0 ; s < Int ; s++){
					this.starArr.push(1)
				}
				console.log(this.starArr)
				if(Point==="0") return
				//利用+將字串轉成數字
				this.starArr.push(+`0.${Point}`);
				console.log(this.starArr)
				
			}
		},
		mounted() {
			this.initStar()
		}
	};
</script>
<style lang="scss" scoped>
	.main {
		display: flex;
		justify-content: center;
	}

	ul#star-box {
		display: flex;
		margin: 0 auto;
		justify-content: space-between;
		padding: 0;

		li {
			display: block;
			list-style: none;
			width: 30px;
			height: 30px;
			background-image: url("../assets/star-64.png");
			background-size: auto 100%;
			margin: 0 3px;

			span {
				display: block;
				width: 0%;
				height: 30px;
				background-image: url("../assets/star.png");
				//指定圖片尺寸
				background-size: auto 100%;
			}
		}
	}

	.test {
		width: 30px;
		height: 30px;
		background-image: url(../assets/pngguru.com.png);
		background-size: auto;
	}
</style>
