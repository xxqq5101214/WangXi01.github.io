<template>
	<div class='hidden-sm-and-down' style="min-width: 200px;">
		<img src="./../assets/logo.png" height="50" style="margin-top: -10px;">
		<div>{{name}}</div>
		<div>{{sign}}</div>
	</div>
</template>

<script>
	export default{
		data(){
			return{
				name:'',
				sign:'',
			}
		},
		mounted: function() {
			this.$nextTick(function() {
				this.init();
			});
		},
		methods: {
			init(){
				//验证登录状态
				this.$http.get('/home').then(res=>{
					this.name = res.data.name;
					this.sign = res.data.sign;
				}).catch(err=>{
					console.log(err)
				})
			},
		}
	}
</script>

