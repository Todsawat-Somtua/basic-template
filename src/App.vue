<script setup>
const positive = 'color: Green'
const negative = 'color: Red'
const accounting = [{
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
</script>

<template>
<table class="border m-7 w-5/12">
    <thead class="bg-slate-400">
        <th>
            Name
        </th>
        <th>
            Amount
        </th>
    </thead>
    <tbody>
        <tr v-for="value in accounting">
            <td class="text-center" v-if="value.amount > 0">
                {{ value.name }} 
            </td>
            <td class="text-center" v-else-if="value.amount < 0">
                {{ value.name }}
            </td>
            <td class="text-center" v-if="value.amount > 0" :style="positive">
                {{ value.amount }} 
            </td>
            <td class="text-center" v-else-if="value.amount < 0" :style="negative">
                {{ value.amount }}
            </td>
        </tr>
    </tbody>
    <tfoot class="text-right ">
        <th>
            Net Total
        </th>
        <th v-for="cost in accounting">
            
        </th>
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