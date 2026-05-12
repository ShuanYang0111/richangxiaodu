```mermaid
graph TD
    %% 节点定义
    Start([开始生产活动]) --> Check{清洁类型?}
    
    %% 日常路径
    Check -- 批清场/日常 --> Daily[使用 75% 无菌异丙醇 - IPA]
    Daily --> Record([记录并存档])
    
    %% 周/月度路径
    Check -- 周大清场/品种切换 --> MonthType{月份属性?}
    
    MonthType -- 单月 --> PlanA[A类方案: 季铵盐/酚类消毒剂]
    MonthType -- 双月 --> PlanB[B类方案: 复合醇类/大泡消]
    
    PlanA --> Spore[强化环节: 每月一次杀孢子剂]
    PlanB --> Spore
    
    Spore --> EM_Check{环境监测 EM 验证}
    
    EM_Check -- 合格 --> Record
    EM_Check -- 不合格 --> Deviation[触发偏差调查与重新清场]
    Deviation --> Start
