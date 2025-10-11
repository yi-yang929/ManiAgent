<script lang="ts" setup>

// 表格数据
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
</script>

<template>
    <div>
        <el-divider />

        <el-row justify="center">
            <h1 class="section-title">More Results</h1>
        </el-row>
        
        <!-- 数据表格 -->
        <el-row justify="center">
            <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">

                <!-- 卡片 -->
                <el-card class="card">

                    <!-- 默认tab -->
                    <el-tabs class="demo-tabs" model-value="Simulation">

                    <!-- 第一个tab -->
                    <el-tab-pane label="Simulation" name="Simulation">

                        <!-- 表格数据 -->
                        <el-table 
                            :data="tableData"
                            :default-sort="{ prop: 'Average', order: 'descending' }"
                            scrollbar-always-on
                        >
                            <el-table-column prop="Method" label="Method" width="180" sortable/>
                            <el-table-column prop="Task_1" label="Task 1" min-width="100" sortable/>
                            <el-table-column prop="Task_2" label="Task 2" min-width="100" sortable/>
                            <el-table-column prop="Task_3" label="Task 3" min-width="100" sortable/>
                            <el-table-column prop="Task_4" label="Task 4" min-width="100" sortable/>
                            <el-table-column prop="Average" label="Average" min-width="100" sortable/>
                        </el-table>
                    </el-tab-pane>

                    <el-tab-pane label="Method B" name="Method B">
                        Method B
                    </el-tab-pane>

                    <!-- <el-tab-pane label="Method C" name="Method C">
                        Method C
                    </el-tab-pane>

                    <el-tab-pane label="Method D" name="Method D">
                        Method D
                    </el-tab-pane> -->
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
</style>
  