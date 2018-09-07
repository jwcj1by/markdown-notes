# 前端开发规范

> ## vue 命名约束

- 常量采用全部大写，单词间下划线分隔的命名方式
- 变量采用驼峰命名法
- 全局属性或者引入文件采用$驼峰命名法进行命名

> ## vue 方法名，计算属性名采用驼峰命名法

```javascript
  computed: {
    conversion () {}
  },
  methods: {
    checkFind () {}
  }
```

> ## vue 组件属性和组件引用采用中划线的方式，枚举变量 使用 Pascal 命名法

```javascript
  <label-content :value="auto_query_condition" label-width="120px" :inline="true" :border="true" label-position="left" label-item-width="400px" all-background="#fbfdff"></label-content>

  import AudioGallery from './mode/audio-gallery.vue' // 音频-Pascal 命名法
  export default {
      components: {'audio-gallery': AudioGallery} // 组件引用采用中划线
  }
```

> ## 选项顺序

```javascript
export default {
  name: '',
  mixins: [], // 混入
  components: {}, // 组件
  model: {},
  props: {},
  data() {
    return {}
  }, // 数据
  created() {}, // 创建周期
  mounted() {}, // dom挂载周期
  computed: {}, // 计算属性
  watch: {}, // 监听器
  methods: {}, // 方法
  filters: {}, // 过滤
  directives: {}, // 指令
  destroyed() {} // 实例销毁周期
}
```

> ## vuex

---

> ### state

```javascript
采用驼峰命名
```

> ### getter

```javascript
// 采用驼峰命名，以get开头
getAllWords (state, getters, rootState, rootGetters) {
  return [...state.words]
}
```

```javascript
// 约束-后缀
// 加载:_LOADING,状态:_STATE,确认:_CONFIRM,弹框:_ALERT,对话框:_DIALOG,赋值:_ASSIGN,通知:_MESSAGE,成功:_SUCCESS,失败:_FAILURE,
// 结账:_CHECKOUT,清除:_CLEAR,重置:_RESET,可用、允许:_ABLE,
// 列表:_LIST,文件:_FILE,任意类型:_ARBIT,数字:_NUMBER,对象:_OBJECT,布尔:_BOOLEAN,日期:_DATE,
// 标记id:_ID,信息:_INFO,编号:_NO,概率:_RATE,约束:_CONSTRAINT,匹配:_MATCH,
// 约束-前缀
// 接收:RECEIVE_,请求:REQUEST_,添加:ADD_TO_,是否:IS_,有无:HAS_,移除:RM_,删除:DEL_,重新:RE_,更新:UPDATE_,
```

> ### mutations

```javascript
// 采用大写声明
export const DATA_RESET = 'DATA_RESET' // 数据重置
[types.DATA_RESET] (state) { // 数据重置
  state.words = []
}
```

> ### actions

```javascript
// 采用驼峰命名，以功能性词汇开头
getWords (context) { // 请求获取works
}
setStateWords (context) {
// 设置
}
```

> ### modules

```javascript
// 采用驼峰命名，以功能性词汇开头
modules: {
  common: {
    namespaced: true, // 根据模块注册的路径调整命名
    modules: {
      wordsStore
    }
  },
  pictureBooks
}
```

##　统一注释

> ## HTML

```HTML
HTML 模块注释:
<!-- 文章列表列表模块 -->
<div class="article-list">
...
</div>

HTML 区块注释:
<!--
@name: Drop Down Menu
@description: Style of top bar drop down menu.
@author: Ashu(Aaaaaashu@gmail.com)
-->
```

> ## Javascript

```javascript
// JS 单行注释:
this.getBaseDataAfter() // 基础数据请求完成之后执行的方法

// JS 多行注释
/**
 * 函数描述
 * 与此函数相关联引入的其他函数，并说明该函数具体位置以及说明其功能
 * @param {string} p1 参数1的说明
 * @param {string} p2 参数2的说明，比较长
 *     那就换行了.
 * @param {number=} p3 参数3的说明（可选）
 * @return {Object} 返回值描述
 */
```

> ## 语义化和命名

```javascript
const HTML_ENTITY = {} // 常量
var loadingModules = {} // 变量
var _privateMethod = {} // 私有属性、变量和方法
function XMLParser() {} // 多个单词组成的 缩写词
import CustomUnit from './config/unit.js' // 枚举变量
```

常用后缀:

```javascript
_id-标记id
_form-表单
_name-标记_id对应的结果/名称
_photo-标记图片
_pdf-PDF文件
_video-视频
_audio-音频
_excel-表格
_number-数字
_date-日期
_info-信息
_rate-概率
_serialnum-编号/_NO-编号
_abel-是否可以Boolean
_remarks-备注
_result-结果
_loading-加载
_alert-弹框
_assign-赋值
_reset-重置
_able-允许
_state-状态
_confirm-确认
_dialog-对话框
_msg-通知
_succ-成功
_err-错误
_failure-失败
_clear-清除
_lists-列表
_file-文件
_infor-信息
_rate-概率
```

常用前缀:
```javascript
is_: 是、可以/否、不可以Boolean
show_: 显示/隐藏Boolean
has_: 有/无Boolean
re_: 重新/再一次
add_to_添加
rm_: 移除
del_: 删除
update_: 更新
up_: 上
down_: 下
req_: 请求
resp_: 响应
receive_: 接收
dis_: 禁止
pre_: 预
sub_: 低、下
co_: 共同、和
ec_: 超出
auto_: 自动
inter_: 之间
mono_: 单独、单一
bith_: 两个、二
tri_: 三
mutil_: 多个
se_: 分离
aph_: 来自
trans_: 通过
pub_: 公共
into_: 输入
intro_: 到...中
all_: 全部
```


```HTML
<pre>
navigation => nav
header => hd
description => desc
button => btn
previous => prev
</pre>
```

css 声明顺序
相关属性应为一组，推荐的样式编写顺序

Positioning（定位）
Box model（盒子模型）
Typographic（排版）
Visual（视觉效果，如动画颜色等）
other（其他）

```CSS
/* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box model */
  display: block;
  box-sizing: border-box;
  width: 100px;
  height: 100px;
  padding: 10px;
  border: 1px solid #e5e5e5;
  border-radius: 3px;
  margin: 10px;
  float: right;
  overflow: hidden;

  /* Typographic */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  color: #fff;
  opacity: .8;

  /* Other */
  cursor: pointer;
```

类型检测优先使用 typeof。对象类型检测使用 instanceof。null 或 undefined 的检测使用 ==

```javascript
// string
typeof variable === 'string'

// number
typeof variable === 'number'

// boolean
typeof variable === 'boolean'

// Function
typeof variable === 'function'

// Object
typeof variable === 'object'

// RegExp
variable instanceof RegExp

// Array
variable instanceof Array

// null
variable === null

// null or undefined
variable == null

// undefined
typeof variable === 'undefined'
```
