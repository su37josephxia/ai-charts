<script setup>
import DataTable from './DataTable.vue'
import { ref, toValue } from 'vue';
const tableData = ref([['', 'Ford', 'Volvo', 'Toyota', 'Honda'], ['2016', 10, 11, 12, 13], ['2017', 20, 11, 14, 13], ['2018', 30, 15, 12, 13]]);
const setInitialData = () => {
    // 输出tableData 去掉所有的空值
    const data = tableData.value.filter((row) => {
        return row.some((cell) => {
            return cell !== null || cell !== '';
        })
    })

    console.log(JSON.stringify(data));
}

</script>
<template>
    <div class="m-5 ">
        <div class="flex flex-row w-full h-full">
            <div class="w-1/2 h-full overflow-x-auto ">
                <DataTable :data="tableData"></DataTable>
            </div>
            <div class="w-1/2 h-full overflow-x-auto">
                <button @click="setInitialData" class="btn btn-primary">设置初始值</button>
            </div>
        </div>
    </div>
</template>