<template>
  <div id="handler">
    <ul>
    	<li @click="numeric_show('(')">(</li>
    	<li @click="numeric_show(')')">)</li>
    	<li @click="show('/')">/</li>
    	<li @click="show('*')">*</li>
    </ul>
    <ul>
    	<li @click="numeric_show(9)">9</li>
    	<li @click="numeric_show(8)">8</li>
    	<li @click="numeric_show(7)">7</li>
    	<li @click="show('-')">-</li>
    </ul>
    <ul>
    	<li @click="numeric_show(4)">4</li>
    	<li @click="numeric_show(5)">5</li>
    	<li @click="numeric_show(6)">6</li>
    	<li @click="show('+')">+</li>
    </ul>
    <ul>
    	<li @click="numeric_show(1)">1</li>
    	<li @click="numeric_show(2)">2</li>
    	<li @click="numeric_show(3)">3</li>
    	<li @click="calc()">=</li>
    </ul>
    <ul>
    	<li @click="clear()"">C</li>
    	<li @click="numeric_show(0)">0</li>
    	<li @click="numeric_show('.')">.</li>
    	<li @click="calc()">=</li>
    </ul>
  </div>
</template>

<script>
	export default {
		props: ['expression'],
		data: function() {
			return {calc_done: false} // 计算状态: true时, nemeric_show 会先清空再展示
		},
		methods: {
			numeric_show: function(value) {
				if(this.calc_done) {
					this.clear();
					this.calc_done = false;
				}
				this.show(value);
			},
			show: function(value) {
				this.calc_done = false;
				this.expression += value;
			},
			calc: function() {
				this.calc_done = true;
				this.expression = eval(this.expression);
			},
			clear: function() {
				this.expression = '';
			}
		}
	}
</script>

<style>

	#handler ul {
		margin: 0;
		padding: 0;
		font-size: 0;
	}
	#handler ul li {
		font-size: 16px;
		margin: 0;
		padding: 0;
		list-style:none;
		display: inline-block;
		width: 24.333333%;
		border: 1px solid #ccc;
		text-align: center;
		height: 50px;
		line-height: 50px;
	}
</style>
