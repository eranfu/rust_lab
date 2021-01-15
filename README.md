# rust_lab

## 无垃圾回收的安全内存管理

- 所有权
    - 每一个值都有一个称为所有者的变量
    - 一个值只能有一个所有者
    - 当所有者超出范围时，该值会被`drop`

- 引用
    - 规则
        - 任何时候，只能有一个可变引用，或者只有任意数量的不可变引用
        - 引用总是有效的
    - slice
    - 引用占用的范围：【绑定引用】到【最后一处使用】

- 生命周期

## 零开销抽象

```
C++的实现遵循“零开销原则”：如果你不使用某个抽象，就不用为它付出开销。
而如果你确实需要使用该抽象，可以保证这是开销最小的使用方式。
                                            — Stroustrup
```

- 特型（Trait）
    - 特型是Rust唯一的接口抽象方式
    - 特型可以静态生成
    - 特型可以动态调用
    - 其它好处
        - Marker
        - 扩展三方库中的类型
        - 实现三方库中的Trait
        - 扩展未知类型

## 无数据竞争（Data Race）风险的并发

- 保证多线程情景下的数据安全
    - Send - 标明某个类型是可以在线程之间进行 `move`
    - Sync - 标明某个类型的引用可以在线程之间进行 `move`
- Mutex
- RwLock
- 仍然_**无法**_在编译期检测到死锁

## 配套工具

- 社区活跃，开源库丰富
    - 文档注释
- 构建工具、包管理器易用且功能丰富（引包、编译、测试、打包、发布）
- IDE
    - Rust官方提供VSCode插件
    - JetBrains提供IDEA内的插件
- 测试
    - 单元测试
    - 集成测试
    - 文档注释测试
    - 覆盖率统计

## 宏

- 独立的模式解析语法
- 可编程宏（Procedural Macro）

## 异步编程

- async/await
