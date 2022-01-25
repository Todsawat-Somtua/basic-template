<script setup>
const positive = 'color: Green'
const negative = 'color: Red'
const accountLists = [{
    name: 'salary',
    amount: 10000
},
{
    name: 'rent',
    amount: -2500
},
{
    name: 'parking fee',
    amount: 0
},
{
    name: 'car fuel',
    amount: -500
},
{
    name: 'commission',
    amount: 5500
}
]
const netTotal = accountLists.reduce(function(previousValue, currentValue) {
    return previousValue + currentValue.amount
}, 0);

</script>

<template>
<table class="border m-7 w-3/6 sm:w-1/12 md:w-4/12 lg:w-8/12">
    <thead class="bg-slate-400">
        <th>
            Name
        </th>
        <th>
            Amount
        </th>
    </thead>
    <tbody>
        <tr v-for="(cost, index) in accountLists" :key="index">
            <td class="text-center" v-if="cost.amount > 0">
                {{ cost.name }} 
            </td>
            <td class="text-center" v-else-if="cost.amount < 0">
                {{ cost.name }}
            </td>
            <td class="text-center" v-if="cost.amount > 0" :style="positive">
                {{ cost.amount }} 
            </td>
            <td class="text-center" v-else-if="cost.amount < 0" :style="negative">
                {{ cost.amount }}
            </td>
        </tr>
    </tbody>
    <tfoot class="text-right ">
        <p class="font-bold">Net Total - {{ netTotal}}</p>
    </tfoot>
</table>

<!-- <div v-for="value in accounting">
    <p v-if="value.amount > 0" :style="positive">{{ value.name }} {{value.amount}}</p>
    <p v-else-if="value.amount < 0" :style="negative">{{ value.name }} {{value.amount}}</p>
    <p v-else></p>
</div> -->
</template>

<style>

</style>