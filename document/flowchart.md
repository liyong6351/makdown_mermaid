# FlowChar-基本语法

## Graph

* 本节讨论graph这种布局模式，这种模式是从上到下的布局

```mermaid
graph TD
    Start --> Stop
```  

1. 本节讨论的是从做到右
2. 关于布局可以有以下选项可供配置:
* TB-top bottom
* BT-bottom top
* RL-right left
* LR-left right
* TD-same as TB

```mermaid
graph LR
    Start --> Stop
```

## 节点和形状

* 默认的节点

```mermaid
graph LR
    id
```

* 拥有描述的文字的节点

```mermaid
graph LR
    id[this is the text in the box]
```

* 拥有形状的节点

```mermaid
graph LR
    id1(this is the text in the box)
```

* 一个圆形的节点

```mermaid
graph LR
    id((this is the text in the circle))
```  

* 一个不对称的形状

```mermaid
graph LR
    id1>this is the text in the box]
```  

* 一个菱形

```mermaid'
graph LR
    id{this is thex in the box}
```  

## 节点之间的连接

* 不同节点之间可以使用连接/边线 进行连接，mermaid提供不同的样式  
* 箭头符号

```mermaid
    graph LR
        A-->B
```

* 不带箭头的符号

```mermaid
graph LR
    A---B
```

* 不带箭头连接上有文字

```mermaid
graph LR
    A-- this is text -->B
```

```mermaid
graph LR
    A---|this is text|B
```

* 带箭头连接上有文字

```mermaid
graph LR
    A-->|This is text|B
```

```mermaid
graph LR
    A-- This is text -->B
```  

* 虚线带文字

```mermaid
graph LR
    A -. text .-B
```

* 实线带文字  

```mermaid
graph LR
    A==>B
```

```mermaid
graph LR
    A== text ==>B
```

* 对于fontawesome基础的支持，通过如下语法：fa:#icon class name#.

```mermaid
graph TD
    B["fa:fa-twitter for peace"]
    B-->C[fa:fa-ban forbidden]
    B-->D(fa:fa-spinner);
    B-->E(A fa:fa-camera-retro perhaps?);
```

```mermaid
graph LR
    A[Hard edge] -->|Link text| B(Round edge)
    B --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
```

```mermaid
graph TB
    sq[Square shape] --> ci((Circle shape))

    subgraph A subgraph
        od>Odd shape]-- Two line<br/>edge comment --> ro
        di{Diamond with <br/> line break} -.-> ro(Rounded<br>square<br>shape)
        di==>ro2(Rounded square shape)
    end

    %% Notice that no text in shape are added here instead that is appended further down
    e --> od3>Really long text with linebreak<br>in an Odd shape]

    %% Comments after double percent signs
    e((Inner / circle<br>and some odd <br>special characters)) --> f(,.?!+-*ز)

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

     classDef green fill:#9f6,stroke:#333,stroke-width:2px;
     classDef orange fill:#f96,stroke:#333,stroke-width:4px;
     class sq,e green
     class di orange
```