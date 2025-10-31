# Context Map (черновик)


> Можно визуализировать через Mermaid в отдельном README или в Miro/Draw.io.


```mermaid
flowchart LR
subgraph WineAssistantCore[Wine Assistant Core]
Catalog[Catalog & Pricing]
ETL[Supplier Price ETL]
end


subgraph OneC[1C Accounting & Tax]
GL[Бухгалтерия]
end


subgraph CRM[CRM/Sales]
CRMApp[CRM]
end


subgraph BI[BI/Analytics]
DWH[Витрины/отчеты]
end


ETL -- нормализованные события/команды --> Catalog
Catalog == ACL ==> OneC
Catalog -- Open-Host Service (REST) --> CRMApp
Catalog -- Events --> BI
