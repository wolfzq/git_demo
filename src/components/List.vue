<template>
    <el-table
      :data="cartData"
      style="width: 100%">
      <el-table-column
        prop="pro_id"
        label="商品编号"
        width="180">
      </el-table-column>
      <el-table-column
        prop="name"
        label="商品名称"
        width="180">
      </el-table-column>
      <el-table-column
        prop="price"
        label="单价"
        width="180">
      </el-table-column>
   
    <el-table-column
      prop="count"
      label="数量"
      width="240" >
      <template slot-scope="scop">
         <el-input-number v-model="scop.row.count" :min="0"></el-input-number>
      </template>
    </el-table-column>

    <el-table-column label="总价">
      <template slot-scope="scop">
        <div>
            {{scop.row.price*scop.row.count}}
        </div>
      </template>
    </el-table-column>
  </el-table>
</template>

<script>
  export default {
      props:{
          cartData:{
              type:Array,
              default:()=>{
                  return[]
              }
          }
      }
  }
</script>
 