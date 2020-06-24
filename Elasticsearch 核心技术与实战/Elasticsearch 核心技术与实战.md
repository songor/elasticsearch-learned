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