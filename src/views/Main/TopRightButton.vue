<template>
    <div>
        <div class="top-right-button"  @click="changeBox" > 三 </div>
        
        <el-drawer 
            v-model="drawer" 
            :with-header="false">
        </el-drawer>
    </div>
</template>

<script>
export default {
    data() {
      return {
        drawer: false,
        activeTab:'User'
      };
    },
    methods: {
        changeBox(){
            // alert("按钮被点击了")
            this.drawer = true
        },
        handleClick(){
            this.handleClick = tab.name
        }
    }
}

</script>

<style lang="scss" scoped>
.top-right-button {
    position: absolute;
    top: 25px;
    right: 25px;

    // 按钮样式
    width: 60px;
    height: 60px;
    border-radius: 50%;
    padding: 20px 20px;
    background-color:rgba(0, 0, 0, 0.2); // 按钮背景颜色
    transition: all 0.3s;
}
.top-right-button:hover {
    background-color: rgba(0, 0, 0, 0.2);
    transform: scale(1.1);
}

// 使用深度选择器修改el-drawer的样式
:deep(.el-drawer__body){
    padding: 0;
}

.divClass{
    height: 90px;
}

.side-header{
    display: flex;
    justify-content: space-between;
    padding: 21px 58px;
    box-sizing: border-box;
    height: 100%;
    width: 100%;
    background-color: aqua;
}
.item{
    padding: 0px 10px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;

    font-size: 12px;
    font-weight: 500;
    color: rgb(51, 51, 51);
    line-height: 17px;
    opacity: 0.4;
    cursor: pointer;
    transition-property: opacity;
    transition-duration: 0.3s;
    transition-timing-function: ease;
    backface-visibility: hidden;
    background-color: red;
}
// 内容
.side-content{

}
</style>