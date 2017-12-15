<style>
.header {
	width: 100%;
	height: 60px;
	padding: 10px;
	line-height: 40px;
	border-bottom: 1px solid #DCDFE6;
	font-size: 16px;
	position: fixed;
	top: 0;
	background-color: #fff;
}
.logo {
	float: left;

}
.status {
	float: right;
}
.nickname {
	margin: 0 10px;
	float: right;
}
.search-input {
	display: inline-block;
	position: absolute;
	left: 50%;
	top: 50%;
	transform: translate(-50%, -50%);
	width: 170px;
	height: 30px;
}
.search-input input {
	width: 170px;
	height: 30px;
	position: absolute;
	left: 50%;
	top: 50%;
	transform: translate(-50%, -50%);
	height: 30px;
	padding: 0 5px 0 25px;
	border-radius: 15px;
	border: 1px solid #DCDFE6;
}
::-webkit-input-placeholder, .search-input i {
   color: #909399;
}
.search-input i {
	position: absolute;
	z-index: 1;
	line-height: 30px;
	left: 5px;
}

.to-top-btn {
	width: 50px;
	height: 50px;
	line-height: 48px;
	border: 1px solid #DCDFE6;
	position: fixed;
	bottom: 60px;
	right: 50px;
	color: #DCDFE6;
	text-align: center;
}
.main {
	margin-top: 60px;
	background-color: #F2F6FC;
}
</style>

<template>
	<div>
		<div class="header">
			<div class="logo">GUN</div>
			<nuxt-link to=""><i class="iconfont icon-editor"></i>编辑</nuxt-link>
			<div class="search-input">
				<i class="iconfont icon-search"></i>
				<input type="" name="" placeholder="搜索">
			</div>
			<nuxt-link to="/sign/in" class="status">SIGN OUT</nuxt-link>
			<div class="nickname">小仙女</div>
		</div>

		
		<a class="to-top-btn" href="#">
			<i class="iconfont icon-jiantoushang"></i>
		</a>

		<div class="main">
			<nuxt/>
		</div>
	</div>
</template>

<script>

</script>
