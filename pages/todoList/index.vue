<template>
	<view class="pubStyle todo-list-title">
    <view class="add-todo-desc">
      添加代办
    </view>
    <view class="add-todo-warp">
      <input v-model="newTodo" class="input-text" type="text" placeholder="添加todolist" confirm-type="search" @confirm="addTodo" />
      <view class="add-todo-button" @click="addTodo">添加</view>
    </view>
		
    <Todo ref="todoRef"></Todo>
	</view>
</template>

<script>
  import Todo from './todo/index.vue'
	export default {
    components: {
      Todo
    },
		data() {
			return {
        newTodo:''
			}
		},
		methods: {
      onEnter() {
        
      },
      addTodo() {
        if(!this.newTodo) {
          uni.showToast({
            icon: 'none',
            title: '请填写代办内容',
            mask: true,
            duration: 2000,
            position: 'bottom'
          })
          return
        }
        // uni.showModal({
        //   title: '提示',
        //   content: this.newTodo,
        //   success(res) {
        //     if (res.confirm) {
        //       console.log('用户点击确定')
        //     } else if (res.cancel) {
        //       console.log('用户点击取消')
        //     }
        //   }
        // })
        this.$refs.todoRef.addTodo({
          date: Date.now(),
          content: this.newTodo,
        })
      }
		},
    onPageScroll: function() {
      // console.log('onPageScroll')
    },
    onReachBottom: function() {
      console.log('onReachBottom')
    },
    onPullDownRefresh: function() {
      console.log('onPullDownRefresh')
    },
	}
</script>

<style lang="scss" scoped>
  .todo-list-title{
    .add-todo-desc{
      font-size: 30rpx;
      color: #666666;
      padding: 5rpx 0;
    }
    .add-todo-warp{
      display: flex;
      font-size: 40rpx;
      line-height: 70rpx;
      .input-text{
        flex: 1;
        padding: 10rpx;
        display: block;
        height: 40rpx;
        width: calc(100% - 10px);
        border: 1rpx solid #ccc;
        box-shadow:  0 0 5rpx 5rpx #E5E5E5;   
        border-radius: 15rpx;
      }
      .add-todo-button{
        height: 70rpx;
        width: 150rpx;
        text-align: center;
        background-color: #0c70ff;
        color: #f8f8f8;
      }
    }
      
  }
</style>
