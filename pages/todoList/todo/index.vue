<template>
	<view class="loading">
    <model-title>
      <template v-slot:title>
        <view>正在进行</view>
      </template>
    </model-title>
    <view class="todo-list-warp">
      <view class="todo-list-item" v-for="(item, index) in todoList">
        <view class="todo-list-item-info">
          <view class="todo-list-item-title">
            创建时间
          </view>
          <view class="todo-list-item-content">
            隋东风
          </view>
        </view>
        
        <view class="todo-list-item-info">
            <view class="todo-list-item-title">
              内容
            </view>
            <view class="todo-list-item-content">
              隋东风
            </view>
        </view>
      </view>
    </view>
	</view>
</template>

<script>
  import ModelTitle from '../../components/ModelTitle/index.vue'
	export default {
    components: {
      ModelTitle
    },
		data() {
			return {
				todoList:[
          {},{}
        ]
			}
		},
		methods: {
			addTodo(newTodo) {
        console.log(newTodo)
      }
		}
	}
</script>

<style lang="scss" scoped>
	.loading{
    color: $uni-text-color;
    background-color: $uni-bg-color-grey;
    .todo-list-warp{
      background: #CDCDCD;
      padding: 10rpx 15rpx;
      .todo-list-item{
        padding: 0 10rpx;
        border-bottom: 1rpx solid #f8f8f8;
        font-size: $uni-font-size-sm;
        color: $uni-text-color;
        line-height: $uni-line-height-sm;
        .todo-list-item-info{
          display: flex;
          .todo-list-item-time{
            
          }
        }
      }
    }
  }
</style>
