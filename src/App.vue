<template>
	<div id="app">
		<img alt="tmp snail" src="./assets/snail.gif">
		<HelloWorld msg="hee-hee how-how"/>

		<div class="baseCalc">
			<form action="" method="" class="form">

				<div class="">
					<label for="basePgBuyValue">PG bottle val(ml)</label>
					<input v-model.number="base.pg.buyValue" type="number" name="basePgBuyValue" id="basePgBuyValue" required>
				</div>
				<div class="">
					<label for="basePgBuyPrice">PG bottle price(rub)</label>
					<input v-model.number="base.pg.buyPrice" type="number" name="basePgBuyPrice" id="basePgBuyPrice" required>
				</div>
				<div class="">
					<label for="baseVgBuyValue">VG bottle val(ml)</label>
					<input v-model.number="base.vg.buyValue" type="number" name="baseVgBuyValue" id="baseVgBuyValue" required>
				</div>
				<div class="">
					<label for="baseVgBuyPrice">VG bottle price(rub)</label>
					<input v-model.number="base.vg.buyPrice" type="number" name="baseVgBuyPrice" id="baseVgBuyPrice" required>
				</div>
				<div class="">
					<label for="baseNicBuyValue">Nic bottle val(ml)</label>
					<input v-model.number="base.nic.buyValue" type="number" name="baseNicBuyValue" id="baseNicBuyValue" required>
				</div>
				<div class="">
					<label for="baseNicBuyPrice">Nic bottle price(rub)</label>
					<input v-model.number="base.nic.buyPrice" type="number" name="baseNicBuyPrice" id="baseNicBuyPrice" required>
				</div>

			<hr>

				<h3> Ароматизаторы:</h3>

			<div class="aromes">
				<ul>
					<!-- <li v-for="arome in aromes" :key="arome.name"> -->
					<li v-bind:key="arome.name" v-for="(arome,index) in aromes">
						<div class="arome">
								<span>{{index+1}}</span>
								<div>
									<p>Название:</p>
									<input v-model="arome.name" type="text" name="Arome">
								</div>
								<div>
									<p>ml флакон:</p>
									<input v-model="arome.buyValue" type="number" name="Arome buyValue">
								</div>
								<div>
									<p>Цена за флакон (rub):</p>
									<input v-model="arome.buyPrice" type="number" name="Arome buyPrice">
								</div>
								<div>
									<p>Количество в миксе (%):</p>
									<input v-model="arome.mixValue" type="number" name="Arome mixPrice">
								</div>
								<button type="button" v-on:click="removeArome(index)">X ({{index}})</button>
						</div>
					</li>
				</ul>
					<button type="button" @click="addArome">Добавить ароматизатор</button>
			</div>

			<hr>


			</form>
		</div>

	</div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
	name: 'app',
	components: {
		HelloWorld
	},
	data: function (){
		return{
			base:{
				pg:{
					buyValue: 1000,
					buyPrice: 200,
					mixValue:0,
					mixPrice:0,

				},
				vg:{
					buyValue: 1000,
					buyPrice: 200,
					mixValue:0,
					mixPrice:0,

				},
				nic:{
					buyValue: 100,
					buyPrice: 400,
					mixValue:0,
					mixPrice:0,

				}
			},
			aromes:[
				{
						name:'Arome # 1',
						buyValue: 1000,
						buyPrice: 200,
						mixValue:0,
						mixPrice:0,
				},
			]

		}
	},
	methods: {
				addArome(){
					 this.aromes.push({name:'Arome #' + (this.aromes.length + 1),buyValue: 12,buyPrice: 170,mixValue:0,mixPrice:0}); // what to push unto the rows array?
				},
				removeArome(index){
					 this.aromes.splice(index,1); // why is this removing only the last row?
				}
		}
}
</script>

<style>
#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 10px;
}

.aromes{
	display: flex;
	flex-flow: column wrap;
	justify-content: flex-start;
}

.arome{
	display: flex;
	flex-flow: row nowrap;
	justify-content: flex-start;
}

.arome p{
	margin-top: 0;
}

</style>
