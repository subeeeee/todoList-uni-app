<script>
export default {
  onLoad: function() {
    console.log('onLoad')
  },
	onLaunch: function() {
    console.log('onLaunch')
	},
	onShow: function() {
    console.log('onShow')
	},
	onHide: function() {
    console.log('onHide')
	},
  onPullDownRefresh: function() {
    console.log('onPullDownRefresh')
  },
  onPageScroll: function() {
    console.log('onPageScroll')
  },
  onTabItemTap: function() {
    console.log('onTabItemTap')
  }
};
</script>

<style lang="scss">
 @import './style/common.scss';
</style>
