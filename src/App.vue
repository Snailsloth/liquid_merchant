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

			

				<div class="mixbottle">
					<h3> Основа:</h3>
					<div class="">
						<label for="basePgMixValue">PG in liq (%)</label>
						<input v-model.number="base.pg.mixValue" type="number" name="basePgMixValue" id="basePgMixValue" required>
					</div>
					<div class="">
						<label for="baseVgMixValue">VG in liq (%)</label>
						<input v-model.number="base.vg.mixValue" type="number" name="baseVgMixValue" id="baseVgMixValue" required>
					</div>
					<div class="">
						<label for="baseNicMixValue">Nic in liq (%)</label>
						<input v-model.number="base.nic.mixValue" type="number" name="baseNicMixValue" id="baseNicMixValue" required>
					</div>
					<Arome :aromes="aromes"/>
				</div>

				



			</form>
		</div>

	</div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Arome from './components/arome.vue'

export default {
	name: 'app',
	components: {
		HelloWorld,Arome
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
</style>
