#### 集成说明
`template `中添加组件
```
<htz-signature @sumbit="sumbit" cid="ceshi1"></htz-signature>
```
`script `中引用组件
```
import htzSignature from '@/components/htz-signature/htz-signature.vue'
export default {
		data() {
			return {
			}
		},
		components: {
			htzSignature,
		},
	}
```

#### 属性说明
|  属性名   | 类型  |  默认值   | 说明  |
|  ----  | ----  |  ----  | ----  |
| cid  | Array | ''  | canvesId(必填！！！) |

#### 事件
 |  事件名称   | 说明  |  回调参数   |
 |  ----  | ----  |  ----  | 
 | sumbit  | 提交成功事件 | Function(res)  | 
 | fail  | 提交失败事件 | Function(err)  | 
 
 #### demo展示
```
<template>
	<view>
		<htz-signature @sumbit="sumbit"  @fail="fail" cid="ceshi1"></htz-signature>
	</view>
</template>
<script>
	import htzSignature from '@/components/htz-signature/htz-signature.vue'
	export default {
		data() {
			return {
			}
		},
		components: {
			htzSignature,
		},
		mounted() {
			this.$nextTick(function() {
			});
	
		},
		methods: {	
			sumbit(res){
				console.log('sumbit',res)
				try {
				    uni.setStorageSync('ceshiUrl', res.tempFilePath);
					uni.navigateBack();
				} catch (e) {
				    // error
				}
			},
			fail(err){
				console.log('fail',err)
			},
		}
	}
</script>
```
#### 备注

1. 组件会自动铺满整个页面
2. 工具栏目前想到的功能就这么多，再有需要的可以在评论下提~
