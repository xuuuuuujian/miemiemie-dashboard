<template>
	<div>
		<el-row :gutter="20">
			<el-col :span="16">
				<el-row :gutter="20" class="mgb20">
					<el-col :span="8">
						<el-card shadow="hover" :body-style="{ padding: '0px' }">
							<div class="grid-content grid-con-1">
								<el-icon class="grid-con-icon"><DocumentChecked /></el-icon>
								<div class="grid-cont-right">
									<div class="grid-num">1234</div>
									<div>在线</div>
								</div>
							</div>
						</el-card>
					</el-col>
					<el-col :span="8">
						<el-card shadow="hover" :body-style="{ padding: '0px' }">
							<div class="grid-content grid-con-3">
								<el-icon class="grid-con-icon"><DocumentDelete /></el-icon>
								<div class="grid-cont-right">
									<div class="grid-num">5000</div>
									<div>离线</div>
								</div>
							</div>
						</el-card>
					</el-col>
					<el-col :span="8">
						<el-card shadow="hover" :body-style="{ padding: '0px' }">
							<div class="grid-content grid-con-2">
								<el-icon class="grid-con-icon"><Files /></el-icon>
								<div class="grid-cont-right">
									<div class="grid-num">6234</div>
									<div>全部</div>
								</div>
							</div>
						</el-card>
					</el-col>
				</el-row>
			</el-col>
		</el-row>
		<el-row :gutter="20">
			<el-col :span="12">
				<el-card shadow="hover">
					<schart ref="line1" class="schart" canvasId="line1" :options="options1"></schart>
				</el-card>
			</el-col>
			<el-col :span="12">
				<el-card shadow="hover">
					<schart ref="line2" class="schart" canvasId="line2" :options="options2"></schart>
				</el-card>
			</el-col>
		</el-row>
		<el-row :gutter="20">
			<el-col :span="12">
				<el-card shadow="hover">
					<schart ref="line3" class="schart" canvasId="line3" :options="options3"></schart>
				</el-card>
			</el-col>
			<el-col :span="12">
				<el-card shadow="hover">
					<schart ref="line4" class="schart" canvasId="line4" :options="options4"></schart>
				</el-card>
			</el-col>
		</el-row>
		<el-row :gutter="20">
			<el-col :span="12">
				<el-card shadow="hover">
					<schart ref="line5" class="schart" canvasId="line5" :options="options3"></schart>
				</el-card>
			</el-col>
			<el-col :span="12">
				<el-card shadow="hover">
					<schart ref="line6" class="schart" canvasId="line6" :options="options4"></schart>
				</el-card>
			</el-col>
		</el-row>
	</div>
</template>

<script setup lang="ts" name="dashboard">
import Schart from 'vue-schart';
import { reactive } from 'vue';
import imgurl from '../assets/img/img.jpg';

const name = localStorage.getItem('ms_username');
const role: string = name === 'admin' ? '超级管理员' : '普通用户';

const options1 = {
	type: 'line',
	title: {
		text: ''
	},
	labels: ['4/4 00:00', '4/4 01:00', '4/4 02:00', '4/4 03:00', '4/4 04:00'],
	datasets: [
		{
			label: '消息流入',
			data: [234, 278, 270, 190, 230]
		}
	]
};
const options2 = {
	type: 'line',
	title: {
		text: ''
	},
	labels: ['4/4 00:00', '4/4 01:00', '4/4 02:00', '4/4 03:00', '4/4 04:00'],
	datasets: [
		{
			label: '消息发出',
			data: [234, 278, 270, 190, 230]
		}
	]
};
const options3 = {
	type: 'line',
	title: {
		text: ''
	},
	labels: ['4/4 00:00', '4/4 01:00', '4/4 02:00', '4/4 03:00', '4/4 04:00'],
	datasets: [
		{
			label: '连接数',
			data: [234, 278, 270, 190, 230]
		}
	]
};
const options4 = {
	type: 'line',
	title: {
		text: ''
	},
	labels: ['4/4 00:00', '4/4 01:00', '4/4 02:00', '4/4 03:00', '4/4 04:00'],
	datasets: [
		{
			label: '主题数',
			data: [234, 278, 270, 190, 230]
		}
	]
};
const options5 = {
	type: 'line',
	title: {
		text: ''
	},
	labels: ['4/4 00:00', '4/4 01:00', '4/4 02:00', '4/4 03:00', '4/4 04:00'],
	datasets: [
		{
			label: '订阅数',
			data: [234, 278, 270, 190, 230]
		}
	]
};
const options6 = {
	type: 'line',
	title: {
		text: ''
	},
	labels: ['4/4 00:00', '4/4 01:00', '4/4 02:00', '4/4 03:00', '4/4 04:00'],
	datasets: [
		{
			label: '消息丢弃',
			data: [234, 278, 270, 190, 230]
		}
	]
};
</script>

<style scoped>
.el-row {
	margin-bottom: 20px;
}

.grid-content {
	display: flex;
	align-items: center;
	height: 100px;
}

.grid-cont-right {
	flex: 1;
	text-align: center;
	font-size: 14px;
	color: #999;
}

.grid-num {
	font-size: 30px;
	font-weight: bold;
}

.grid-con-icon {
	font-size: 50px;
	width: 100px;
	height: 100px;
	text-align: center;
	line-height: 100px;
	color: #fff;
}

.grid-con-1 .grid-con-icon {
	background: rgb(45, 140, 240);
}

.grid-con-1 .grid-num {
	color: rgb(45, 140, 240);
}

.grid-con-2 .grid-con-icon {
	background: #515a6e;
}

.grid-con-2 .grid-num {
	color: #515a6e;
}

.grid-con-3 .grid-con-icon {
	background: rgb(242, 94, 67);
}

.grid-con-3 .grid-num {
	color: rgb(242, 94, 67);
}

.user-info {
	display: flex;
	align-items: center;
	padding-bottom: 20px;
	border-bottom: 2px solid #ccc;
	margin-bottom: 20px;
}

.user-info-cont {
	padding-left: 50px;
	flex: 1;
	font-size: 14px;
	color: #999;
}

.user-info-cont div:first-child {
	font-size: 30px;
	color: #222;
}

.user-info-list {
	font-size: 14px;
	color: #999;
	line-height: 25px;
}

.user-info-list span {
	margin-left: 70px;
}

.mgb20 {
	margin-bottom: 20px;
}

.todo-item {
	font-size: 14px;
}

.todo-item-del {
	text-decoration: line-through;
	color: #999;
}

.schart {
	width: 100%;
	height: 300px;
}
</style>
