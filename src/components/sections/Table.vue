<script lang="ts" setup>

// 第一个表格数据
const tableData = [
{
    Method: 'CogACT',
    Task_1: '15.0%',
    Task_2: '50.8%',
    Task_3: '71.7%',
    Task_4: '67.5%',
    Average: '51.3%',
},
{
    Method: 'pi-0',
    Task_1: '21.3%',
    Task_2: '58.8%',
    Task_3: '63.3%',
    Task_4: '79.2%',
    Average: '55.7%',
},
{
    Method: 'ManiAgent-GPT-4o',
    Task_1: '76.4%',
    Task_2: '95.8%',
    Task_3: '77.8%',
    Task_4: '47.2%',
    Average: '74.3%',
},
{
    Method: 'ManiAgent-GPT-5-nano',
    Task_1: '72.2%',
    Task_2: '63.9%',
    Task_3: '62.5%',
    Task_4: '50.0%',
    Average: '62.2%',
},
{
    Method: 'ManiAgent-GPT-5',
    Task_1: '87.5%',
    Task_2: '95.8%',
    Task_3: '91.7%',
    Task_4: '72.2%',
    Average: '86.8%',
},
{
    Method: 'ManiAgent-Claude-4-sonnet',
    Task_1: '77.8%',
    Task_2: '98.6%',
    Task_3: '80.6%',
    Task_4: '62.5%',
    Average: '79.9%',
},
{
    Method: 'ManiAgent-Grok-4',
    Task_1: '88.9%',
    Task_2: '98.6%',
    Task_3: '83.3%',
    Task_4: '61.1%',
    Average: '83.0%',
}
]

// 第二个表格数据
const tableData2 = [
{
    Type: 'Commercial VLM',
    Method: 'GPT-4o',
    Task_1: '5/6',
    Task_2: '5/6',
    Task_3: '3/6',
    Task_4: '4/6',
    Task_5: '4/6',
    Task_6: '3/6',
    Task_7: '4/6',
    Task_8: '2/6',
    Average: '62.5%',
},
{
    Type: 'Commercial VLM',
    Method: 'GPT-5-nano',
    Task_1: '5/6',
    Task_2: '6/6',
    Task_3: '4/6',
    Task_4: '6/6',
    Task_5: '4/6',
    Task_6: '4/6',
    Task_7: '4/6',
    Task_8: '3/6',
    Average: '75.0%',
},
{
    Type: 'Commercial VLM',
    Method: 'GPT-5',
    Task_1: '6/6',
    Task_2: '6/6',
    Task_3: '6/6',
    Task_4: '6/6',
    Task_5: '6/6',
    Task_6: '5/6',
    Task_7: '4/6',
    Task_8: '6/6',
    Average: '93.8%',
},
{
    Type: 'Commercial VLM',
    Method: 'Claude-4-sonnet',
    Task_1: '6/6',
    Task_2: '6/6',
    Task_3: '6/6',
    Task_4: '5/6',
    Task_5: '6/6',
    Task_6: '6/6',
    Task_7: '6/6',
    Task_8: '5/6',
    Average: '95.8%',
},
{
    Type: 'Commercial VLM',
    Method: 'Grok-4',
    Task_1: '6/6',
    Task_2: '6/6',
    Task_3: '4/6',
    Task_4: '6/6',
    Task_5: '6/6',
    Task_6: '6/6',
    Task_7: '6/6',
    Task_8: '6/6',
    Average: '95.8%',
},
{
    Type: 'Opensource VLM',
    Method: 'GPT-oss-120b',
    Task_1: '4/6',
    Task_2: '6/6',
    Task_3: '2/6',
    Task_4: '4/6',
    Task_5: '4/6',
    Task_6: '2/6',
    Task_7: '2/6',
    Task_8: '1/6',
    Average: '52.1%',
},
{
    Type: 'Opensource VLM',
    Method: 'Qwen-3-235b',
    Task_1: '6/6',
    Task_2: '5/6',
    Task_3: '1/6',
    Task_4: '6/6',
    Task_5: '3/6',
    Task_6: '2/6',
    Task_7: '1/6',
    Task_8: '2/6',
    Average: '54.2%',
}
]

// 单元格样式方法
// 合并单元格样式方法
const mergedCellStyle = ({row, column, rowIndex, columnIndex}) => {
    const baseStyle = {
        padding: '5px'
    };
    
    if (rowIndex % 2 === 0) {
        return {
            ...baseStyle,
            backgroundColor: '#EFEFEF'
        }
    }
    
    return baseStyle;
}

</script>

<template>
    <div>
        <el-divider />

        <el-row justify="center">
            <h1 class="section-title">More Results</h1>
        </el-row>
        
        <!-- 数据表格 -->
        <el-row justify="center">
            <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="10">
                <!-- 卡片 -->
                <el-card class="card">
                    <!-- 默认tab -->
                    <el-tabs class="demo-tabs" model-value="Simulation">
                        <!-- 第一个tab -->
                        <el-tab-pane label="Simulation" name="Simulation">
                            <!-- 表格数据 -->
                            <el-table 
                                :justify="center"
                                :data="tableData"
                                :default-sort="{ prop: 'Average', order: 'descending' }"
                                :header-cell-style="{ backgroundColor: '#f5f7fa' }"
                                :row-style="{ height: '50px' }"
                                :cell-style="{ padding: '5px' }"
                                style="width: 100%; table-layout: fixed;"
                                :fit="false"
                                :scrollbar-always-on="true"
                                :show-header="true"
                            >
                                <el-table-column prop="Method" label="Method" width="180" sortable/>
                                <el-table-column prop="Task_1" label="Task 1" min-width="100" sortable/>
                                <el-table-column prop="Task_2" label="Task 2" min-width="100" sortable/>
                                <el-table-column prop="Task_3" label="Task 3" min-width="100" sortable/>
                                <el-table-column prop="Task_4" label="Task 4" min-width="100" sortable/>
                                <el-table-column prop="Average" label="Average" min-width="100" sortable/>
                            </el-table>
                        </el-tab-pane>

                        <!-- 第二个tab -->
                        <el-tab-pane label="Physical Experiments" name="Physical">
                            <!-- 表格数据 -->
                            <el-table 
                                :justify="center"
                                :data="tableData2"
                                :default-sort="{ prop: 'Average', order: 'descending' }"
                                :cell-style="mergedCellStyle"
                                :header-cell-style="{ backgroundColor: '#f5f7fa' }"
                                :row-style="{ height: '50px' }"
                                style="width: 100%; table-layout: fixed;"
                                :fit="false"
                                :scrollbar-always-on="true"
                                :show-header="true"
                            >
                                <el-table-column prop="Type" label="Type" width="150"/>
                                <el-table-column prop="Method" label="Method" width="150"/>
                                <el-table-column prop="Task_1" label="Task 1" min-width="80" sortable/>
                                <el-table-column prop="Task_2" label="Task 2" min-width="80" sortable/>
                                <el-table-column prop="Task_3" label="Task 3" min-width="80" sortable/>
                                <el-table-column prop="Task_4" label="Task 4" min-width="80" sortable/>
                                <el-table-column prop="Task_5" label="Task 5" min-width="80" sortable/>
                                <el-table-column prop="Task_6" label="Task 6" min-width="80" sortable/>
                                <el-table-column prop="Task_7" label="Task 7" min-width="80" sortable/>
                                <el-table-column prop="Task_8" label="Task 8" min-width="80" sortable/>
                                <el-table-column prop="Average" label="Average" min-width="100" sortable/>
                            </el-table>
                        </el-tab-pane>
                    </el-tabs>
                </el-card>
            </el-col>
        </el-row>
    </div>
</template>

<style scoped>
.card {
    margin-top: 20px;
}

/* 表格容器样式 */
.el-table {
    width: 100% !important;
    table-layout: fixed !important;
}

/* 表头和表体容器样式 */
.el-table__header-wrapper,
.el-table__body-wrapper {
    overflow-x: auto !important;
    position: relative !important;
}

/* 确保表头和表体宽度一致 */
.el-table__header,
.el-table__body {
    width: 100% !important;
    table-layout: fixed !important;
}

/* 修复表头和表体不对齐的核心样式 */
.el-table__body-wrapper::-webkit-scrollbar,
.el-table__header-wrapper::-webkit-scrollbar {
    height: 8px !important;
}

.el-table__body-wrapper::-webkit-scrollbar-thumb,
.el-table__header-wrapper::-webkit-scrollbar-thumb {
    background: #c0c4cc;
    border-radius: 4px;
}

/* 表格单元格样式 */
.el-table th,
.el-table td {
    padding: 8px 0 !important;
    text-align: center !important;
}

/* 修复表格边框 */
.el-table--border::after,
.el-table--group::after,
.el-table::before {
    background-color: #EBEEF5;
}

/* 修复表格行样式 */
.el-table__row {
    height: 50px !important;
}

/* 修复表头样式 */
.el-table__header {
    width: 100% !important;
    table-layout: fixed !important;
}

/* 修复表体样式 */
.el-table__body {
    width: 100% !important;
    table-layout: fixed !important;
}
</style>
