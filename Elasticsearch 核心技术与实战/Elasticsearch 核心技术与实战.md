# Elasticsearch 核心技术与实战

### 05 | Elasticsearch 的安装与简单配置

* 运行单个实例

  `.\bin\elasticsearch`

  http://localhost:9200/

* 安装插件

  `.\bin\elasticsearch-plugin list`

  `.\bin\elasticsearch-plugin install analysis-icu`

  https://artifacts.elastic.co/downloads/elasticsearch-plugins/analysis-icu/analysis-icu-7.4.0.zip

  `.\bin\elasticsearch-plugin install file:///C:\develop\elasticsearch-plugins\analysis
  -icu-7.8.0.zip`

  http://localhost:9200/_cat/plugins

* 运行多个实例

  ```powershell
  .\bin\elasticsearch -E node.name=node0 -E cluster.name=geektime -E path.data=node0_data -d
  .\bin\elasticsearch -E node.name=node1 -E cluster.name=geektime -E path.data=node1_data -d
  .\bin\elasticsearch -E node.name=node2 -E cluster.name=geektime -E path.data=node2_data -d
  ```
  
  http://localhost:9200/_cat/nodes

### 06 | Kibana 的安装与界面快速浏览

`.\bin\kibana.bat`

http://localhost:5601/

### 08 | Logstash 安装与导入数据

`.\bin\logstash -f .\config\logstash.conf`

### 09 | 基本概念：索引、文档和 REST API

* 文档

  Elasticsearch 是面向文档的，文档是所有可搜索数据的最小单位

  文档会被序列化成 JSON 格式，保存在 Elasticsearch 中

  每个文档都有一个 Unique ID

* 元数据

  \_index，\_type，\_id，\_source，\_version，\_score

* 索引

  索引是文档的容器，是一类文档的结合

  逻辑空间的概念

  Mapping 定义文档字段的类型

  Setting 定义不同的数据分布

* REST API

  `GET movies`

  `GET movies/_count`

  `POST movies/_search`