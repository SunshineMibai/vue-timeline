<template>
	<div class='time'>
		<div class='text-content'>
			<h2 class='text-center'>Vue时间轴demo</h2>
			<div class='time-line'>
				<div v-for='item in testList' class='time-line-div'>
					<p>{{item.time}}</p>
					<p ref='circular'></p>
					<p>{{item.text}}</p>
				</div>
				<div class='img-dotted' ref='dotted'></div>
			</div>
			<div style='margin-top:20px;'>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				testList:[
				{key:'1',time:'2001-01-01 01:00:00',text:'第一步第一步第一步第一步第一步'},
				{key:'2',time:'2002-02-02 02:00:00',text:'第二步第二步第二步第二步第二步'},
				{key:'3',time:'2003-03-03 03:00:00',text:'第三步第三步第三步第三步第三步'},
				{key:'4',time:'2004-04-04 04:00:00',text:'第四步第四步第四步第四步第四步'},
				{key:'5',time:'2005-05-05 05:00:00',text:'第五步第五步第五步第五步第五步'}
				]
			}
		},
		mounted() {
			this.$refs.dotted.style.left = this.$refs.circular[0].offsetLeft - 12 + 'px'
		}
	}
</script>

<style>
.text-center{
	text-align: center;
}
.time h2{
	color:#FF6600;
	margin: 20px auto 30px auto;
}
.time-line{
	position: relative;
	width:300px;
	margin:0 auto;
}
.time-line-div{
	position:relative;
	min-height:85px;
}
.time-line-div>p:nth-child(1){
	position: absolute;
	left:0;
	width:100px;
}
.time-line-div>p:nth-child(2){
	position:absolute;
	left: 100px;
	width:15px;
	height:15px;
	top:10px;
	background:#5CB85C;
	border-radius: 50%;
	z-index: 10
}
.time-line-div>p:nth-child(3){
	position:absolute;
	left: 130px;
	padding: 10px;
	background: #317EF3;
	font-size:.8rem;
	color:#fff;
	border-radius: 10px;
}
.img-dotted{
	position:absolute;
	width:20px;
	height:100%;
	top:0;
	z-index: 1;
	background:url('/static/dotted.png');
}
</style>