# element-ui-table-spancol
基于element-ui的table的表格的合并行和列
## 基于

```javascript
<script setup lang="ts">
import spanRow from 'spancol'
const data = [
  { field1: "营业收费系统", field2: "中国农业银行", field3: "2022-03", filed4: '2022-03-04', filed5: '4' },
  { field1: "营业收费系统", field2: "中国农业银行", field3: "2022-03", filed4: '2022-03-05', filed5: '2' },
  { field1: "营业收费系统", field2: "中国农业银行", field3: "2022-03", filed4: '2022-03-06', filed5: '2' },
  { field1: "营业收费系统", field2: "中国农业银行", field3: "2022-03", filed4: '2022-03-07', filed5: '2' },
  { field1: "营业收费系统", field2: "中国农业银行", field3: "小计", filed4: '', filed5: '2' },
  { field1: "营业收费系统", field2: "中国建设银行", field3: "2022-04", filed4: '2022-04-05', filed5: '3' },
  { field1: "营业收费系统", field2: "中国建设银行", field3: "2022-04", filed4: '2022-04-06', filed5: '2' },
  { field1: "营业收费系统", field2: "中国建设银行", field3: "2022-04", filed4: '2022-04-07', filed5: '2' },
  { field1: "营业收费系统", field2: "中国建设银行", field3: "2022-04", filed4: '2022-04-08', filed5: '2' },
  { field1: "营业收费系统", field2: "中国建设银行", field3: "小计", filed4: '', filed5: '2' },
  { field1: "营业收费系统", field2: "小计", field3: "", filed4: '', filed5: '1' },

  { field1: "报装管理系统", field2: "中国农业银行", field3: "2022-03", filed4: '2022-03-04', filed5: '12' },
  { field1: "报装管理系统", field2: "中国农业银行", field3: "2022-03", filed4: '2022-03-05', filed5: '21' },
  { field1: "报装管理系统", field2: "中国农业银行", field3: "2022-03", filed4: '2022-03-06', filed5: '21' },
  { field1: "报装管理系统", field2: "中国农业银行", field3: "2022-03", filed4: '2022-03-07', filed5: '21' },
  { field1: "报装管理系统", field2: "中国农业银行", field3: "小计", filed4: '', filed5: '6' },
  { field1: "报装管理系统", field2: "中国建设银行", field3: "2022-04", filed4: '2022-04-05', filed5: '11' },
  { field1: "报装管理系统", field2: "中国建设银行", field3: "2022-04", filed4: '2022-04-06', filed5: '53' },
  { field1: "报装管理系统", field2: "中国建设银行", field3: "2022-04", filed4: '2022-04-07', filed5: '53' },
  { field1: "报装管理系统", field2: "中国建设银行", field3: "2022-04", filed4: '2022-04-08', filed5: '53' },
  { field1: "报装管理系统", field2: "中国建设银行", field3: "小计", filed4: '', filed5: '32' },
  { field1: "报装管理系统", field2: "小计", field3: "", filed4: '', filed5: '23' },
]
const option = [
  { index: 0, field: "field1" },
  { index: 1, field: "field2" },
  { index: 2, field: 'field3' }
]
const onSpanMethod = ({ row, column, rowIndex, columnIndex }: any) => {
  return spanRow(
    { row, column, rowIndex, columnIndex },
    data,
    option
  );
}
<script setup lang="ts">
```


```html

 <el-table
        id="printJS-table"
        class="border"
        :data="data"
        border
        :span-method="onSpanMethod"
        height="100%"
      >
        <el-table-column prop="field1" label="field1"></el-table-column>
        <el-table-column prop="field2" label="field2"></el-table-column>
        <el-table-column prop="field3" label="field3"></el-table-column>
        <el-table-column prop="filed4" label="filed4"></el-table-column>
        <el-table-column prop="filed5" label="filed5"></el-table-column>
      </el-table>
      <el-button @click="printHtml">打印</el-button>
    </div>
```