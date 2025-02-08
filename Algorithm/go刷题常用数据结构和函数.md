## 常用数据结构
### 字符串
#### 高效拼接
```go
var b bytes.Buffer
b.WriteString("Hello ")
b.WriteString("World")
b1 := b.String()

// 多个字符串拼接
var strs []string
strings.Join(strs, "World")
```
#### 查询是否属于特定字符串
```go
// 判断是否包含元音
if strings.Contains("aeiouAEIOU", string(s[i])) {
    // ...
}
```

#### 字符串转换
```go
strconv.Itoa(int)  // int -> string
strconv.Atoi(str)  // string -> int
```
#### 字符串分割
```go
// 字符串分割
strings.Splie(str, str2) // 将str按str2作为分隔符进行分割，返回字符串切片
```
```go
// 大小写切换
strings.ToLower(str) // string全部转为小写
strings.ToUppe(str)  // str全部转为大写
```

### Slice
#### 添加数据
```go
// 在尾部添加元素
slice = append(slice, 1)
```
#### 模拟Stack
```go
// 创建栈
stack := make([]int, 0)
// push压入
stack = append(stack, 10)
// pop弹出
v := stack[len(stack) - 1]
stack = stack[:len(stack) - 1]
// 检查栈空
len(stack) == 0
```

#### 模拟Queue
```go
// 创建队列
queue := make([]int, 0)
// enqueue入队
queue = append(queue, 10)
// dequeue出队
v := queue[0]
queue = queue[1:]
// 长度0为空
len(queue) == 0
```

### Map
```go
// 创建
m := make(map[keyType]ValueType)
// 设置kv
m["hello"] = 1
// 删除k
delete(m,"hello")
```
## 常用函数
### sort
```go
// int排序
sort.Ints([]int{})
// 字符串排序
sort.Strings([]string{})
// 进行反转
sort.Reverse()
```
自定义比较器`sort.Search`,通过二分法，找到满足条件（即函数返回值为true）的最小的索引
```go
index := sort.Search(n, func(i int) bool {
	// ...
})
```

### math
```go
 // int32 最大最小值
math.MaxInt32
math.MinInt32
// int64 最大最小值（int默认是int64）
math.MaxInt64
math.MinInt64
```
### copy
```go
// 删除a[i]，可以用 copy 将i+1到末尾的值覆盖到i,然后末尾-1
copy(a[i:], a[i+1:])
a = a[:len(a)-1]
```
