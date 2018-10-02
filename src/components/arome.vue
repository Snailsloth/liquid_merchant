<template>

<div class="aromes">
    <h3> Ароматизаторы:</h3>
    <hr>
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

<hr>

</div>

</template>

<script>

export default {
    name: 'Arome',
    props: ["aromes"],
    template: '',
    data: function () {
        return {
            
        }
    },
    methods: {
            addArome(){
                    this.aromes.push({name:'Arome #' + (this.aromes.length + 1),buyValue: 12,buyPrice: 170,mixValue:0,mixPrice:0});
            },
            removeArome(index){
                    this.aromes.splice(index,1);
            }
        },
        created:function(){

            console.log(this.aromes);
        }
}

</script>

<style scoped>
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
