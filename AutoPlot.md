1.GPT + PlantUML自动代码绘图：

PlantUML是一种可以基于给定代码自动绘图的框架，可以由gpt生成代码来实现自动绘图，prompt参考：

> 针对以下内容使用 PlantUML语法，选择最适合呈现内容中的逻辑关系的图表格式并生成对应的代码，并给出选择该图表的理由：

绘制后的图像可以在[PlantUML官方在线绘图](https://www.plantuml.com/plantuml/uml/)中实时绘制和调整。

PlantUML另一个优点是可以在[PlantUML官方免费模板库](https://real-world-plantuml.com/)中找到与自己需求相近的图表，然后直接交给GPT修改为自己的内容。

***

2.结合GPT + Mermaid.js + Markdown实现自动绘图：

可以使用GPT的prompt来实现自动生成给定内容的Mermaid.js代码并基于Markdown绘制对应的图表：

> 针对以下内容 **[段落]**使用 mermaid.js 语法，生成一个**[图表类型]**示范。
>
> 针对以下内容，使用 mermaid.js 语法，选择最适合呈现内容中的逻辑关系的图表格式并生成对应的代码，可选的图表包括：流程图、序列图、类图、状态图、实体关系图、用户旅程图、甘特图、饼图、象限图、需求图、Gitgraph图、C4图、思维导图、时间线图、Zenuml图和桑基图，并给出选择该图表的理由：

Mermaid.js是一个生成流程图、序列图、甘特图等图表的 JavaScript 库。以下是使用 Mermaid.js 可以绘制的图表类型以及对应的示例代码。

如果要修改图表的**字体颜色**等格式，可以参考：[Mermaid主题列表](https://mermaid.nodejs.cn/config/theming.html)

1. 流程图 (Flowchart)
```mermaid
graph TD
    A[Start] --> B{Is it sunny?}
    B -->|Yes| C[Go to the park]
    B -->|No| D[Stay home]
```
2. 序列图 (Sequence Diagram)
```mermaid
sequenceDiagram
    participant 初步阶段 as 初步阶段：实时数据采集系统开发
    participant 边控技术应用 as 边缘计算技术应用
    participant 数据收集 as 关键环境参数和能源消耗数据收集
    participant 调控算法研发 as 智能调控算法研发
    participant 环境模型构建 as 能源消耗与环境效应模型构建
    participant 节能平台开发 as 综合节能优化平台开发
    participant 案例研究与验证 as 多个植物工厂案例研究和系统验证

    初步阶段->>边控技术应用: 开展
    边控技术应用->>数据收集: 收集数据
    数据收集->>调控算法研发: 分析数据
    调控算法研发->>环境模型构建: 开发算法
    环境模型构建->>节能平台开发: 构建模型
    节能平台开发->>案例研究与验证: 开发平台
    案例研究与验证->>初步阶段: 验证与评估
```
3. 甘特图 (Gantt Diagram)
```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```
4. 类图 (Class Diagram)
```mermaid
classDiagram
    Class01 <|-- AveryLongClass : Cool
    Class03 *-- Class04
    Class05 o-- Class06
    Class07 .. Class08
    Class09 --> C2 : Where am i?
    Class09 --* C3
    Class09 --|> Class07
    Class07 : equals()
    Class07 : Object[] elementData
    Class01 : size()
    Class01 : int chimp
    Class01 : int gorilla
    Class08 <--> C2: Cool label
```
5. 状态图 (State Diagram)
```mermaid
stateDiagram
    [*] --> Still
    Still --> [*]
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```
6. 用户旅程图 (User Journey Diagram)
```mermaid
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```
7. 实体关系图 (Entity Relationship Diagram)
```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER {
        string name
        string id
    }
    ORDER {
        string date
        string id
        int total
    }
    LINE-ITEM {
        number quantity
        float unit-price
    }
```

8. 饼图 (Pie Chart)
```mermaid
pie
    title Pie Chart
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```
9. 象限图 (Quadrant Diagram)
```mermaid
quadrantChart
    title Reach and engagement of campaigns
    x-axis Low Reach --> High Reach
    y-axis Low Engagement --> High Engagement
    quadrant-1 We should expand
    quadrant-2 Need to promote
    quadrant-3 Re-evaluate
    quadrant-4 May be improved
    Campaign A: [0.3, 0.6]
    Campaign B: [0.45, 0.23]
    Campaign C: [0.57, 0.69]
    Campaign D: [0.78, 0.34]
    Campaign E: [0.40, 0.34]
    Campaign F: [0.35, 0.78]

```
10. 需求图 (Requirement Diagram)
```mermaid
requirementDiagram
    requirement test_req {
        id: 1
        text: "The system call"
        risk: high
    }
    functionalRequirement test_func {
        id: 2
        text: "Functions"
        risk: medium
    }
    requirement test_req2 {
        id: 3
        text: "Others"
        risk: low
    }
    test_req - satisfies -> test_func
    test_req2 - satisfies -> test_func
```
11. Gitgraph (Git) 图
```mermaid
---
title: Example Git diagram
---
gitGraph
   commit
   commit
   branch develop
   checkout develop
   commit
   commit
   checkout main
   merge develop
   commit
   commit

```
12. C4 图
```mermaid
 C4Deployment
  title 烟草企业安全管理部署图

  Deployment_Node(tech, "技术层面", "异常检测、响应机制") {
    Container(tech_strategy, "技术策略", "AI/ML模型", "利用异常检测技术进行实时监控，快速识别潜在安全威胁，并建立由大型语言模型生成的有效应急响应机制。")
  }

  Deployment_Node(org, "组织层面", "安全管理体系") {
    Container(org_strategy, "组织策略", "政策、规程、培训", "建立明确的安全政策、操作规程、培训机制和监督措施，提升员工的安全意识和应急处理能力。")
  }

  Deployment_Node(culture, "文化层面", "安全文化建设") {
    Container(culture_strategy, "文化策略", "领导示范、持续改进", "将安全理念融入企业文化，培养员工的安全文化意识，建立持续改进的文化氛围。")
  }

  Rel(tech_strategy, org_strategy, "整合于", "技术和组织")
  Rel(org_strategy, culture_strategy, "包含", "组织和文化")

  Deployment_Node(tobacco, "烟草企业", "企业环境") {
    Deployment_Node(tech_layer, "技术层面实施", "安全技术实施") {
      Container(tech_impl, "技术实施", "AI/ML模型、异常检测", "实施安全技术进行实时监控和威胁识别。")
    }
    Deployment_Node(org_layer, "组织层面实施", "管理体系实施") {
      Container(org_impl, "组织实施", "政策、规程、培训", "实施包括政策、规程和培训机制的全面安全管理体系。")
    }
    Deployment_Node(culture_layer, "文化层面实施", "文化整合实施") {
      Container(culture_impl, "文化实施", "领导示范、持续改进", "通过领导示范和不断改进，实施文化整合。")
    }
  }



```
13. 思维导图 (Mindmap)
```mermaid
mindmap
  root((mindmap))
    Origins
      Long history
      ::icon(fa fa-book)
      Popularisation
        British popular psychology author Tony Buzan
    Research
      On effectiveness<br/>and features
      On Automatic creation
        Uses
            Creative techniques
            Strategic planning
            Argument mapping
    Tools
      Pen and paper
      Mermaid


```
14. 时间线图 (Timeline)
```mermaid
timeline
    title History of Social Media Platform
    2002 : LinkedIn
    2004 : Facebook
         : Google
    2005 : Youtube
    2006 : Twitter
```
15. Zenuml
```mermaid
zenuml
    title Demo
    Alice->John: Hello John, how are you?
    John->Alice: Great!
    Alice->John: See you later!
```
16. 桑基图 (Sankey Diagram)
```mermaid
sankey-beta

Bio-conversion,Losses,26.862

Bio-conversion,Solid,280.322

Bio-conversion,Gas,81.144

```

17. XY图（XYChart）

    ```mermaid
    xychart-beta
            title "Sales Revenue"
            x-axis [jan, feb, mar, apr, may, jun, jul, aug, sep, oct, nov, dec]
            y-axis "Revenue (in $)" 4000 --> 11000
            bar [5000, 6000, 7500, 8200, 9500, 10500, 11000, 10200, 9200, 8500, 7000, 6000]
            line [5000, 6000, 7500, 8200, 9500, 10500, 11000, 10200, 9200, 8500, 7000, 6000]
    ```

    ***
    
    3.其他代码绘图或者手动绘图网站：
    
    1. [draw.io](https://draw.io/) - 一个免费的在线图表绘制工具，支持流程图、UML图、ER图等多种图表类型，用户界面直观，支持多人协作。
    2. [LucidChart](https://www.lucidchart.com/) - 一个强大的在线图表绘制和数据可视化平台，提供丰富的图表类型和模板，支持团队协作，适合专业和商业用途。
    3. [ProcessOn](https://www.processon.com/) - 一个在线协作绘图平台，提供流程图、思维导图、UML图等多种绘图工具，适合团队协作和项目管理。
    4. [Zen Flowchart](https://www.zenflowchart.com/) - 一个简单易用的在线流程图绘制工具，界面简洁，支持导出和分享，适合快速创建流程图。
    5. [Code-flowchart.js](https://flowchart.js.org/) - 一个基于 JavaScript 的工具，可以将代码转换为流程图，支持多种编程语言，有助于理解和可视化代码结构。
    6. [Code-js-sequence-diagrams](https://bramp.github.io/js-sequence-diagrams/) - 一个 JavaScript 库，用于将文本转换为序列图，适用于文档和演示文稿中的快速序列图绘制。
    7. [Code-websequence](https://www.websequencediagrams.com/) - 一个在线序列图绘制工具，允许用户通过文本来描述和生成序列图，支持自定义样式和导出功能。
    8. [Code-yuml.me](https://yuml.me/) - 一个在线UML图绘制工具，可以通过简单的文本语法来创建类图、序列图和用例图等，支持直接在浏览器中编辑和分享。
