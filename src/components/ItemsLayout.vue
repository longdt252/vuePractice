<template>
  <div class="col-md-9">
    <div class="bg-table">
        <table class="table">
            <thead class="thead-light">
                <tr class="tr-table">
                    <th scope="col">STT</th>
                    <th scope="col">Tên</th>
                    <th scope="col">Action</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item,index) in propsItems" :key="index" class="tr-item" :data="item">
                    <td>{{ index + 1 }}</td>
                    <td>{{ item }}</td>
                    <td><button @click.stop="delItem(index)" class="btn btn-danger">Del</button></td>
                </tr>
            </tbody>
        </table>
    </div>
  </div>
</template>

<script>

export default {
    name: 'ItemsLayout',
    props: ['propsItems'],
    methods: {
        delItem(index){
            this.$emit('deleted-item', index);
        },
    },
}
</script>

<style scoped>
.bg-table{
    border: 1px solid #eee;
    padding: 10px;
    margin-top: 20px;
    background: #fafafa;
}
table{
    background: #fff;
    margin: 0px;
    border: 1px solid #dee2e6;
}
 .tr-table th:nth-child(1){
     width: 10%;
 }
  .tr-table th:nth-child(2){
     width: 70%;
 }
  .tr-table th:nth-child(3){
     width: 20%;
 }
 .tr-item:hover{
     cursor: pointer;
     background: #fafafa;
 }
 .tr-item:last-child{
     border-bottom: 1px solid #dee2e6;
 }
 button:hover{
    cursor: pointer;
 }
 .table td, .table th{
    vertical-align: middle;
 }
</style>