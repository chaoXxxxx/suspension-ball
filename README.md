# suspension-ball

## 可滑动的悬浮球

### template
```
<suspension-ball 
    @eventEmit="eventEmit" 
    @positionEmit="positionEmit" 
    :zIndex="1002" 
    :distance="{top: 70, left: 10, right: 25, bottom: 10}" 
    :init="{top: 80}">
        <div class="float_ball">悬浮</div>
</suspension-ball>

import suspensionBall from 'suspensionBall'
```

### typescript
```
import { Component, Vue } from 'vue-property-decorator'
import { Position } from './types/app'
import SuspensionBall from '../src/components/SuspensionBall.vue'

@Component({
  components: {
    SuspensionBall
  }
})
export default class App extends Vue {
  private eventEmit(): void {
    return
  }

  private positionEmit(position: Position): void {
    console.log(`top => ${position.top}  left => ${position.left}`)
  }
}
```

### 参数
```
// 组件层级 (如果碰到滑动问题，请检查 z-index。z-index需比web大一级) 默认1001
@Prop({
    type: Number,
    required: false,
    default: 1001
}) private zIndex !: number

// 初始化距离 (组件默认位置top, left)
@Prop({
    type: Object,
    required: false,
    default: () => {
      return {
        top: 0,
        left: 0
      }
    }
}) private init !: Init

// 组件距离 (组件距离上右下左的边距)
@Prop({
    type: Object,
    required: false,
    default: () => {
        return {
            top: 10,
            left: 10,
            right: 10,
            bottom: 10
        }
    }
}) private distance !: Distance
```

### 源码
```
[suspension-ball](https://gitee.com/ChaoXxxx/suspension-ball). 
```