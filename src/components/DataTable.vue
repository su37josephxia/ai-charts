<template>
    <div class="custom-data-table">
        <hot-table :data="data" :rowHeaders="true" :colHeaders="true" :contextMenu="true" :stretchH="all"
            :stretchV="all" :height="600" :width="800" licenseKey="non-commercial-and-evaluation"
            copyPaste="true"></hot-table>
    </div>
</template>

<script>
import { defineComponent } from 'vue';
import { HotTable } from '@handsontable/vue3';
import { registerAllModules } from 'handsontable/registry';
import 'handsontable/styles/handsontable.min.css';
import 'handsontable/styles/ht-theme-main.min.css';

// register Handsontable's modules
registerAllModules(

);

export default defineComponent({
    props: {
        data: {
            type: Array,
            default: () => []
        }
    },
    components: {
        HotTable,
    }
});
</script>

<style scoped>
.custom-data-table {
    /* 这里可以添加自定义样式 */
    border: 1px solid #ccc;
    padding: 10px;
}
</style>