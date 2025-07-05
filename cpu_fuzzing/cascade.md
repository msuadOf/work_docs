## 摘要
- 提出了cascade，能生成随机化、相互依赖的指令流
- 长程序更有效
## 1.简介
- cpu fuzzing程序
- bug检测：简单说了下difftest的思路，然后说他不好，只在结束的时候对比，不能监控中间状态
- cascade引入：我们的是随机riscv程序生成器，引入了非对称isa预模拟。
- 三个特性：程序很长，提高性能；探索不寻常的数据和控制流；通过高度关联的程序，让程序跑不到最后，就直接崩了，就不用像difftest那种有运行时开销
- 成果：薄纱
- 自动程序剪枝器：会迭代，触发bug后会有挂起、错误的值、exceptions、decode issue、性能计数器不精确
## 2.背景
### 2.1 硬件形式化验证
计算成本高、人工成本高
### 2.2 软件fuzzing
- fuzzer需要一个策略生成测试用例
- 依赖于某种形式的coverage feedback、静态/动态taint分析、语法
- bug检测：crash、sanitizer
### 2.3 硬件fuzzing
- 目前sanitizer程序仅限于sv assertion
- crash法是在程序末尾用store指令dump寄存器组值，然后和ISS比对
- diff法是。。。
## 3.动机和挑战（文章的TODOS）
### 3.1 发现
### 3.2 挑战
