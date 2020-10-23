<template>
  <div class="col-md-3">
    <form>
        <div class="form-group">
            <label for="ipName">Tên sản phẩm</label>
            <input v-model="itemInput" type="text" class="form-control" id="ipName" placeholder="Nhập sản phẩm">
        </div>
        <button type="submit" class="btn btn-primary" @click.prevent="addItem">Thêm</button>
    </form>
  </div>
</template>

<script>

export default {
    name: 'AddItem',
    props: ['propsItems'],
    data: () => {
        return {
            itemInput: '',
        }
    },
    methods: {
        addItem(){
            if(this.itemInput == ''){
                alert("Không được để trống!")
                 return false;
            } else if (this.propsItems.length >= 10){
                alert("Không được nhập quá 10 sản phẩm!")
                return false;
            }
            else if(this.propsItems.includes(this.itemInput)){
                alert("Không được nhập trùng!")
                return false;
            }
            else {
                this.$emit('item-added', this.itemInput);
                this.itemInput = '';
            }
        },
    },
}
</script>

<style scoped>
    form{
        border: 1px solid #eee;
        margin-top: 20px;
        padding: 20px;
        text-align: left;
        font-size: 12px;
    }
    input{
        font-size: 14px;
    }
    button{
        font-size: 14px;
        width: 100%;
    }
</style>