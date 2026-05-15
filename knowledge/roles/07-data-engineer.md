# Data Engineer — Skill Framework

## Tổng quan
- **Tên role:** Data Engineer
- **Level:** Junior → Mid → Senior → Lead
- **Mô tả:** Thiết kế, xây dựng và vận hành pipeline dữ liệu quy mô lớn. Làm việc với SQL, Python/Scala, Spark, Airflow, dbt, Data Warehouse (Snowflake/BigQuery/Redshift), Data Lake, Kafka, Stream Processing. Đảm bảo dữ liệu sạch, đúng hạn, sẵn sàng cho phân tích và machine learning.
- **Tags:** data-engineer, sql, python, spark, etl, airflow, dbt, snowflake, bigquery, kafka, data-lake, data-warehouse, stream-processing

## Kỹ năng theo cấp độ

### Level 1: Junior (0-2 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | SQL cơ bản | SELECT, JOIN (INNER/LEFT/RIGHT/FULL), GROUP BY, HAVING, subquery, UNION, window function cơ bản (ROW_NUMBER, RANK), CASE WHEN, CTE | 25% | sql, database, postgresql, mysql |
| 2 | Python cơ bản cho Data | Biến, list, dict, set, loop, function, file I/O (csv, json, parquet), pandas cơ bản (read/write, filter, groupby, merge), requests | 25% | python, pandas, numpy |
| 3 | ETL cơ bản | Khái niệm Extract-Transform-Load, batch processing cơ bản, incremental vs full load, error handling cơ bản, scheduling với cron | 20% | etl, batch, pipeline |
| 4 | Data Modeling cơ bản | Normalization (1NF/2NF/3NF), Star Schema cơ bản (Fact vs Dimension), Primary Key, Foreign Key, ERD | 15% | data-modeling, star-schema, normalization |
| 5 | Git & CI/CD cơ bản | Git workflow (clone, branch, commit, merge, PR), GitHub/GitLab, code review, CI/CD concepts | 10% | git, version-control, cicd |
| 6 | Cloud cơ bản | AWS S3 / GCP Cloud Storage / Azure Blob Storage, IAM cơ bản, Console navigation | 5% | cloud, aws, gcp, azure |

### Level 2: Mid (2-4 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | SQL nâng cao | Window functions (LAG/LEAD, PARTITION BY, ROWS/RANGE), recursive CTE, PIVOT/UNPIVOT, query execution plan (EXPLAIN), indexing strategy (B-tree, Hash, Partition), materialized view | 20% | sql, advanced-sql, query-optimization |
| 2 | Data Warehouse | Snowflake (Virtual Warehouse, Time Travel, Zero-copy Clone) / BigQuery (Partitioned Tables, Clustering, Slot) / Redshift (Distribution Key, Sort Key, Vacuum), ELT vs ETL, data modeling trong DWH (Kimball Star Schema, Slowly Changing Dimensions Type 0/1/2/3) | 20% | snowflake, bigquery, redshift, data-warehouse, kimball, scd |
| 3 | Apache Spark (PySpark/Scala Spark) | DataFrame API, RDD fundamentals, Spark SQL, partition & shuffle, broadcast join vs sort-merge join, Spark UI debugging, optimization (caching, persist, checkpoint), Spark Submit | 20% | spark, pyspark, scala, big-data |
| 4 | Orchestration (Airflow/dagster/Prefect) | DAG design, Operator (Python/Bash/Sensor), scheduling (cron), backfill, XCom, task dependencies, retry & SLA, dynamic DAG, monitoring | 15% | airflow, orchestration, workflow, scheduling |
| 5 | dbt (data build tool) | Model (SQL), source, ref, macro, Jinja templating, test (unique, not_null, accepted_values), snapshot (SCD Type 2), incremental model, materialization (table/view/incremental/ephemeral), dbt docs | 10% | dbt, transformation, analytics-engineering |
| 6 | Cloud Data Services | AWS (Glue, Athena, EMR, Lambda, Step Functions) / GCP (Dataflow, Dataproc, Cloud Composer, Pub/Sub) / Azure (Data Factory, Synapse, Databricks), managed vs self-managed trade-off | 10% | cloud, aws-glue, gcp-dataflow, azure-data-factory |
| 7 | Container & DevOps cơ bản | Docker (Dockerfile, image, container, docker-compose), CI/CD cho data pipeline (testing data, schema validation), Infrastructure as Code cơ bản (Terraform) | 5% | docker, devops, terraform |

### Level 3: Senior (4-7 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Stream Processing | Kafka (Topic, Partition, Offset, Consumer Group, Exactly-Once Semantics, Kafka Connect, Schema Registry), Spark Structured Streaming (watermark, output mode, stateful operations), Kafka Streams / Flink fundamentals, event time vs processing time, late data handling | 25% | kafka, stream-processing, flink, real-time |
| 2 | Data Lake Architecture | Lakehouse (Delta Lake, Iceberg, Hudi), ACID trên Data Lake, time travel, schema evolution, partition evolution, Medallion Architecture (Bronze/Silver/Gold), Data Mesh vs centralized | 20% | data-lake, delta-lake, iceberg, lakehouse, medallion |
| 3 | Data Quality & Governance | Data quality dimensions (Accuracy, Completeness, Consistency, Timeliness, Uniqueness, Validity), validation framework (Great Expectations, Soda, dbt tests), data lineage (OpenLineage, Marquez, Atlus), data catalog (DataHub, Amundsen), anomaly detection | 20% | data-quality, governance, lineage, data-catalog |
| 4 | Hiệu năng & Tối ưu Spark | Data skew handling, salting, broadcast join threshold tuning, dynamic resource allocation, shuffle partition tuning, query plan analysis (DAG visualization), memory management (executor/driver memory, off-heap), AQE (Adaptive Query Execution) | 15% | spark-optimization, performance, data-skew |
| 5 | Monitoring & Observability | Data pipeline monitoring (latency, freshness, volume, schema changes), alerting (Slack/PagerDuty), logging (structured logging, log aggregation), metrics (Prometheus + Grafana), data SLAs | 10% | monitoring, observability, alerting, data-sla |
| 6 | Advanced Data Modeling | Data Vault 2.0 (Hub, Link, Satellite), Anchor Modeling, dimensional modeling cho complex hierarchies (Ragged, Parent-Child), data fabric concepts | 10% | data-modeling, data-vault, dimensional-modeling |

### Level 4: Lead/Principal (7+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Data Platform Architecture | Thiết kế end-to-end data platform (ingestion → storage → transformation → serving), make vs buy decisions (self-hosted vs managed services), multi-cloud/hybrid strategy, platform modularity và composability | 25% | architecture, data-platform, strategy |
| 2 | Team Leadership | Xây dựng data engineering team từ đầu, hiring & retention strategy, career framework cho data engineer, code review culture, mentoring junior/senior, cross-team collaboration với Data Science & Analytics | 20% | leadership, management, team-building |
| 3 | Data Strategy & Roadmap | Xây dựng data roadmap (short-term wins + long-term vision), data maturity assessment (DAMA, CMMI), ROI analysis cho data initiatives, stakeholder alignment (VP Engineering, CDO, CTO) | 20% | strategy, roadmap, data-maturity |
| 4 | Data Governance Framework | Thiết kế data governance operating model, PII & GDPR/CCPA compliance, access control (RBAC/ABAC, row-level security, column-level security), data retention policy, data contract (schema enforcement), data product ownership | 15% | governance, compliance, rbac, data-contract |
| 5 | Cost Optimization & FinOps | Cloud cost attribution (tag-based cost allocation), warehouse compute optimization (slot usage, auto-suspend, clustering), storage lifecycle management (hot/warm/cold), pipeline efficiency (incremental processing, partition pruning), budget planning | 10% | finops, cost-optimization, cloud-cost |
| 6 | Stakeholder Communication | Executive presentation (roadmap, trade-off, cost), cross-functional alignment (Data Science, Analytics, Product, Engineering), vendor relationship management, incident communication (RCAs, post-mortem) | 10% | communication, stakeholder, presentation |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### SQL
#### Basic
- "Viết query lấy top 10 sản phẩm có doanh thu cao nhất trong tháng gần nhất, kèm % đóng góp vào tổng doanh thu."
- "Phân biệt INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN và CROSS JOIN? Cho ví dụ thực tế khi dùng từng loại."
- "WHERE vs HAVING khác nhau thế nào? Khi nào dùng HAVING?"
- "UNION vs UNION ALL khác nhau thế nào? Khi nào nên dùng UNION ALL?"
- "Viết query tìm khách hàng đã mua hàng trong 3 tháng liên tiếp?"

#### Medium
- "ROW_NUMBER() vs RANK() vs DENSE_RANK() khác nhau thế nào? Cho ví dụ mỗi loại."
- "LAG và LEAD dùng để làm gì? Viết query tính % thay đổi doanh thu tháng này so với tháng trước."
- "Recursive CTE là gì? Viết query hiển thị cây phân cấp tổ chức từ CEO đến nhân viên."
- "Giải thích cách đọc EXPLAIN plan? Làm sao để biết query có đang dùng index không?"
- "Làm sao tối ưu query bị chậm? Các bước phân tích cụ thể?"

#### Advanced
- "Thiết kế schema cho hệ thống phân tích hành vi người dùng web/app (event tracking) với 1 tỷ events/ngày. Chọn database nào? Tại sao?"
- "So sánh Columnar Storage (BigQuery, Snowflake) vs Row-based Storage (PostgreSQL, MySQL) cho analytical workloads? Tại sao columnar tốt hơn?"
- "Làm sao xử lý Slowly Changing Dimensions trong SQL thuần (không dùng dbt snapshot)? Implement Type 1 và Type 2 bằng SQL."
- "Phân tích và tối ưu một query phức tạp với 5 JOIN trên bảng vài tỷ dòng: tối ưu join order, CTE vs subquery, partition pruning."

### Python cho Data
#### Basic
- "Xử lý file CSV 10GB bằng Python — làm thế nào để không bị OOM? Các thư viện hỗ trợ?"
- "Pandas: merge, join, concat khác gì? Khi nào dùng cái nào?"
- "List comprehension vs Generator expression khác gì? Viết generator đọc file CSV từng dòng."
- "Làm sao xử lý missing values trong pandas? fillna, interpolate, dropna?"

#### Medium
- "Làm sao xử lý dữ liệu JSON lồng nhau phức tạp trong pandas? json_normalize dùng thế nào?"
- "Vectorized operations trong pandas là gì? Tại sao nhanh hơn apply/iterrows?"
- "Multiprocessing vs Multithreading vs AsyncIO trong Python — khi nào dùng cái nào cho data processing?"
- "Dask/Polars là gì? Khi nào nên upgrade từ pandas lên Dask/Polars?"
- "Làm sao viết unit test cho data pipeline? Mock database connection, test transformation logic."

#### Advanced
- "Viết custom partitioner cho PySpark để giải quyết data skew trên cột có phân phối không đều."
- "So sánh PySpark DataFrame API vs Spark SQL vs RDD — khi nào dùng cái nào? Và bên trong Spark SQL compile thế nào?"
- "Xử lý 100TB dữ liệu với Python mà không dùng Spark — những lựa chọn có thể?"
- "Thiết kế Python-based stream processing framework từ scratch — cần xử lý những vấn đề gì? (checkpoint, backpressure, state management)"

### ETL / ELT
#### Basic
- "Phân biệt ETL và ELT? Khi nào chọn ETL, khi nào chọn ELT?"
- "Full Load vs Incremental Load khác gì? Các chiến lược incremental load phổ biến?"
- "Làm sao xử lý duplicate data trong ETL pipeline?"
- "Handling errors trong ETL: retry, dead-letter queue, alerting?"

#### Medium
- "Slowly Changing Dimensions (SCD) Type 0, 1, 2, 3, 4, 6 là gì? Cho ví dụ thực tế mỗi loại."
- "UPSERT (MERGE) pattern trong ETL — implement thế nào trên các database khác nhau?"
- "Backfill dữ liệu lịch sử 5 năm vào data warehouse mới — chiến lược và các lưu ý?"
- "Làm sao validate data pipeline output? Data reconciliation, row count check, checksum?"

#### Advanced
- "Thiết kế real-time ETL pipeline xử lý CDC (Change Data Capture) từ PostgreSQL lên Snowflake với latency < 1 phút."
- "So sánh các CDC tool: Debezium, Fivetran, Airbyte, AWS DMS, Striim — tiêu chí chọn?"
- "Xử lý schema evolution trong ETL pipeline: source schema thay đổi thì làm sao pipeline không break?"
- "Thiết kế multi-tenant ETL architecture: isolation, performance, cost optimization?"

### Apache Spark
#### Basic
- "Spark RDD vs DataFrame vs Dataset khác gì? Khi nào dùng cái nào?"
- "Giải thích Transformations (narrow vs wide) và Actions trong Spark? Tại sao Spark lazy evaluation?"
- "Các chế độ deploy Spark: local, standalone, YARN, Kubernetes — khác gì?"
- "Caching và Persist trong Spark: cache() vs persist(), storage levels (MEMORY_ONLY, MEMORY_AND_DISK...)"

#### Medium
- "Shuffle trong Spark là gì? Tại sao shuffle tốn kém? Làm sao giảm shuffle?"
- "Broadcast Join vs Sort-Merge Join vs Shuffle Hash Join — khi nào Spark chọn cái nào?"
- "Data Skew là gì? Làm sao phát hiện và xử lý data skew trong Spark?"
- "Spark partition optimization: coalesce() vs repartition(), spark.sql.shuffle.partitions tuning."
- "Spark UI: đọc Stages, Tasks, Executors tab để troubleshooting job chậm?"

#### Advanced
- "Spark Adaptive Query Execution (AQE): Cơ chế hoạt động? Dynamically coalescing shuffle partitions, skew join optimization."
- "Spark Memory Management: On-heap vs Off-heap, UnifiedMemoryManager, OOM troubleshooting."
- "Structured Streaming: watermark, output mode (append/update/complete), state store (HDFS vs RocksDB)."
- "So sánh Spark vs Trino/Presto vs Flink — mỗi tool phù hợp với use case nào?"
- "Thiết kế pipeline processing 1TB/ngày với Spark: partition strategy, memory config, error handling, monitoring."

### Airflow / Orchestration
#### Basic
- "Airflow DAG, Task, Operator là gì? Viết DAG đơn giản đọc CSV → transform → load vào DB."
- "Các loại Operator trong Airflow: PythonOperator, BashOperator, Sensor, BranchOperator, trigger rules."
- "Schedule interval trong Airflow: cron expression, @daily, @hourly. Catchup là gì?"

#### Medium
- "Airflow Executor: Sequential vs Local vs Celery vs Kubernetes Executor — khác gì? Khi nào upgrade?"
- "XCom dùng để làm gì? Giới hạn của XCom? Alternative cho passing large data giữa tasks?"
- "Airflow DAG dependencies: TriggerDagRunOperator, ExternalTaskSensor, Dataset (Airflow 2.4+)."
- "Monitoring & Alerting trong Airflow: SLA miss, task failure callback, integration với Slack/PagerDuty."
- "Dynamic DAG generation trong Airflow: khi nào cần? Các pattern phổ biến?"

#### Advanced
- "Thiết kế multi-tenant Airflow: isolation giữa các team, resource management, cost allocation."
- "Airflow scalability: bottleneck thường gặp (scheduler, metadata DB, executor) và cách giải quyết?"
- "So sánh Airflow vs Dagster vs Prefect vs Temporal — dựa trên các tiêu chí: DX, scalability, observability, data-aware scheduling."
- "Thiết kế data pipeline orchestration cho 10,000 DAGs chạy hàng ngày — cần lưu ý kiến trúc gì?"

### dbt (data build tool)
#### Basic
- "dbt là gì? dbt hoạt động ở layer nào trong data stack hiện đại (ELT)?"
- "Phân biệt model, source, seed, snapshot trong dbt?"
- "dbt materialization: table, view, incremental, ephemeral — khi nào dùng cái nào?"
- "dbt test: built-in tests (unique, not_null, accepted_values, relationships) vs custom tests?"

#### Medium
- "dbt incremental model hoạt động thế nào? is_incremental() macro, merge strategy."
- "dbt snapshot dùng để làm gì? Implement SCD Type 2 với snapshot."
- "Jinja trong dbt: ref(), source(), config(), var(), macro — cách viết DRY code?"
- "dbt data lineage (DAG) — làm sao dbt tự động tạo DAG giữa các model? ref() hoạt động thế nào?"

#### Advanced
- "Thiết kế dbt project structure cho tổ chức 50+ data analysts/engineers — monorepo vs multi-repo, package management, CI/CD."
- "dbt performance optimization: materialization strategy, incremental strategy, cluster key, partition pruning."
- "dbt Mesh và data contracts — làm sao enforce contract giữa source và consumer trong dbt?"
- "CI/CD cho dbt: Slim CI, defer to production, data diff, schema change detection."

### Data Warehouse (Snowflake / BigQuery / Redshift)
#### Basic
- "So sánh Snowflake vs BigQuery vs Redshift — kiến trúc chính khác gì?"
- "Snowflake Virtual Warehouse, Storage, Cloud Services layer — mỗi layer làm gì?"
- "Phân biệt Columnar vs Row-based storage? Tại sao data warehouse dùng columnar?"

#### Medium
- "Snowflake Time Travel, Fail-safe, Zero-copy Clone — giải thích và use case?"
- "Partitioning và Clustering trong BigQuery: partition by date vs cluster by column, khi nào dùng cái nào?"
- "Redshift Distribution Style (KEY, ALL, EVEN, AUTO) và Sort Key — tối ưu thế nào?"
- "Snowflake micro-partition là gì? Pruning hoạt động thế nào?"
- "Làm sao tối ưu cost trong Snowflake/BigQuery? Warehouse size, auto-suspend, slot reservation."

#### Advanced
- "Thiết kế multi-cluster warehouse architecture: load balancing, workload isolation (ELT cluster vs BI cluster), query prioritization."
- "Data Sharing trong Snowflake vs BigQuery — kiến trúc và use case cross-organization?"
- "Migration strategy từ on-premise data warehouse (Teradata/Oracle/Netezza) lên cloud — các giai đoạn và risk?"
- "So sánh Snowflake Snowpark vs Spark vs dbt cho transformation — khi nào dùng cái nào?"

### Kafka / Stream Processing
#### Basic
- "Kafka Topic, Partition, Offset, Producer, Consumer, Consumer Group — giải thích từng khái niệm."
- "Kafka vs RabbitMQ vs Pub/Sub — khác biệt chính? Khi nào dùng Kafka?"
- "Kafka message delivery semantics: at-most-once, at-least-once, exactly-once — giải thích và trade-off."

#### Medium
- "Kafka Partition assignment strategy: Range vs RoundRobin vs Sticky vs Cooperative Sticky."
- "Kafka Producer: acks=0 vs acks=1 vs acks=all, idempotent producer, compression (gzip, snappy, lz4, zstd)."
- "Kafka Consumer Rebalancing là gì? Làm sao giảm thời gian rebalance?"
- "Schema Registry: Avro, Protobuf, JSON Schema — schema evolution và compatibility (BACKWARD, FORWARD, FULL)."
- "Kafka Connect: Source Connector vs Sink Connector, Single Message Transform (SMT), Dead Letter Queue."

#### Advanced
- "Thiết kế event-driven data platform dùng Kafka làm backbone: event modeling, schema design, partitioning strategy, disaster recovery (MirrorMaker, multi-region)."
- "Kafka Streams vs Apache Flink vs Spark Structured Streaming — so sánh chi tiết về state management, exactly-once, latency, scalability, operational complexity."
- "Watermark và Late Data Handling trong Stream Processing: cho phép delay bao lâu? Làm gì với data đến muộn?"
- "Kafka exactly-once semantics: làm sao đạt được end-to-end exactly-once từ producer → consumer? Transaction API, idempotent consumer."
- "Thiết kế real-time fraud detection system với Kafka + Flink — latency < 100ms, throughput 100k events/s."

### Data Modeling
#### Basic
- "Phân biệt OLTP vs OLAP modeling? ERD chuẩn hóa (3NF) vs Star Schema?"
- "Fact Table vs Dimension Table — khác gì? Cho ví dụ trong e-commerce."
- "Giải thích các loại Fact: Transactional, Periodic Snapshot, Accumulating Snapshot."
- "Surrogate Key vs Natural Key — khi nào dùng surrogate key?"

#### Medium
- "Slowly Changing Dimensions Type 1, 2, 3 — implement từng loại trong SQL và dbt."
- "Degenerate Dimension, Junk Dimension, Role-Playing Dimension — là gì? Cho ví dụ."
- "Star Schema vs Snowflake Schema vs Galaxy Schema — trade-off?"
- "Design dimensional model cho bài toán Order Management: xác định dimension, fact, grain."

#### Advanced
- "Data Vault 2.0: Hub, Link, Satellite — triết lý thiết kế? So sánh với Kimball Star Schema."
- "Khi nào chọn Data Vault thay vì Star Schema? Trade-off về query performance, agility, auditability."
- "Anchor Modeling là gì? So sánh với Data Vault và Kimball?"
- "Thiết kế dimensional model cho bài toán Insurance (Policies, Claims, Premiums) — xử lý many-to-many dimensions, heterogeneous facts."
- "Data Mesh: Data Product, Domain Ownership, Federated Governance — Data Model thay đổi thế nào trong Data Mesh?"

### Data Quality & Governance
#### Basic
- "Data Quality 6 dimensions: Accuracy, Completeness, Consistency, Timeliness, Uniqueness, Validity — giải thích từng cái."
- "Data Freshness là gì? Làm sao monitor data freshness trong pipeline?"
- "Data Profiling là gì? Những metric cần kiểm tra khi profiling data?"

#### Medium
- "Great Expectations: Expectations, Validation Results, Data Docs, Checkpoint — workflow cơ bản."
- "Data Lineage: Column-level vs Table-level lineage, OpenLineage, Marquez — tại sao cần?"
- "Data Catalog: DataHub vs Amundsen vs Atlan vs Alation — tiêu chí chọn?"
- "Làm sao implement schema validation trong data pipeline? Contract testing cho data."

#### Advanced
- "Thiết kế Data Governance Operating Model cho tổ chức 500+ nhân viên: roles (Data Owner, Data Steward, Data Custodian), processes, tools."
- "Data Contract: thiết kế và enforce data contract giữa producer và consumer trong microservice architecture."
- "GDPR/CCPA compliance trong data pipeline: Right to be forgotten, data retention, PII masking/anonymization — implement thế nào?"
- "Data Observability vs Data Quality vs Data Governance — mối quan hệ và tool overlap?"

### Cloud Data Services
#### Basic
- "AWS Glue là gì? Glue Data Catalog, Crawler, ETL Job — workflow cơ bản."
- "AWS S3 storage classes: Standard, Intelligent-Tiering, Glacier — khi nào dùng cái nào cho data lake?"
- "IAM Policy cơ bản cho S3 bucket: bucket policy vs user policy."

#### Medium
- "AWS Glue Studio vs AWS Glue Script (PySpark) — khi nào dùng visual ETL, khi nào code?"
- "GCP Dataflow (Apache Beam): Windowing, Trigger, Watermark — xử lý streaming data thế nào?"
- "Azure Data Factory: Pipeline, Activity, Linked Service, Integration Runtime — kiến trúc?"
- "Athena vs Redshift Spectrum vs Presto/Trino — query data trên S3, khác biệt và use case?"

#### Advanced
- "Thiết kế multi-cloud data platform (AWS + GCP): data replication, unified catalog, disaster recovery, cost comparison."
- "Serverless Data Architecture: AWS Lambda + Step Functions vs Managed Services (Glue/EMR) — trade-off về cost, performance, cold start."
- "Data security trên cloud: encryption at rest (KMS), encryption in transit (TLS), network security (VPC, PrivateLink), audit logging (CloudTrail)."
- "Migration từ on-premise Hadoop ecosystem lên cloud-native — chiến lược lift-and-shift vs re-architecture."

## Dự án mẫu để lấp gap

### Level Junior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "ETL Pipeline: CSV/S3 → PostgreSQL" | Python, pandas, SQL, ETL pipeline, S3, error handling | 2-3 tuần | Python, pandas, PostgreSQL, AWS S3, Docker |
| 2 | "Data Warehouse Star Schema cho E-Commerce" | SQL, Star Schema, dimensional modeling, data loading | 2-3 tuần | PostgreSQL/MySQL, SQL, Python (psycopg2/SQLAlchemy) |
| 3 | "Web Scraping + Data Pipeline cho Job Listings" | Python (requests/BeautifulSoup/Scrapy), pandas, data cleaning, scheduling | 3-4 tuần | Python, Scrapy, pandas, SQLite/PostgreSQL, cron |
| 4 | "API Data Ingestion Pipeline (Weather Data)" | REST API, Python, JSON handling, incremental load, scheduling | 2-3 tuần | Python, requests, PostgreSQL, Docker, cron/Airflow cơ bản |
| 5 | "Data Quality Dashboard cơ bản" | SQL, data profiling, pandas, visualization (Streamlit/Grafana) | 3-4 tuần | Python, pandas, Streamlit, PostgreSQL, Docker |

### Level Mid — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "End-to-End ELT Pipeline với Airflow + dbt + Snowflake" | Airflow DAG, dbt transformation, Snowflake DWH, SCD Type 2, data testing, scheduling | 4-6 tuần | Airflow, dbt, Snowflake (hoặc BigQuery), Python, S3/GCS |
| 2 | "Real-time Clickstream Processing với Kafka + Spark Streaming" | Kafka (Producer/Consumer), Spark Structured Streaming, data serialization (Avro), Schema Registry, real-time aggregation | 6-8 tuần | Kafka, Spark Streaming, Avro, Schema Registry, Python, Docker |
| 3 | "Data Lake: Medallion Architecture trên S3 + Spark" | Spark (PySpark), Parquet, Delta Lake, Bronze/Silver/Gold layers, partition optimization, data quality | 6-8 tuần | PySpark, Delta Lake, AWS S3/EMR, Great Expectations, Docker |
| 4 | "Cloud-native ETL Pipeline: AWS Glue + Step Functions + Redshift" | AWS Glue ETL, Step Functions orchestration, Redshift, S3 data lake, IAM, CloudWatch | 4-6 tuần | AWS Glue, Step Functions, Redshift, S3, Python, Terraform |
| 5 | "Data Pipeline CI/CD với dbt + GitHub Actions" | dbt project structure, Jinja macros, dbt tests, Slim CI, data diff, schema change detection | 3-4 tuần | dbt, Snowflake/BigQuery, GitHub Actions, Docker |

### Level Senior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Real-time Data Platform: CDC → Kafka → Flink → Data Lake + DWH" | CDC (Debezium), Kafka, Flink/Spark Streaming, Apache Iceberg, Data Vault 2.0, multi-hop architecture | 10-12 tuần | Kafka, Flink/Spark Streaming, Iceberg, Debezium, Snowflake, dbt, K8s |
| 2 | "Data Observability Platform" | Data quality monitoring, freshness SLA, anomaly detection, lineage tracking, alerting, self-service dashboard | 8-10 tuần | Great Expectations/Soda, DataHub/Marquez/OpenLineage, Prometheus, Grafana, Python, SQL |
| 3 | "Multi-tenant Data Platform Architecture" | Tenant isolation (row-level vs schema-level vs database-level), resource management, cost attribution, security (RBAC, data masking), cross-tenant analytics | 8-12 tuần | Snowflake/BigQuery, dbt, Airflow, Terraform, Python, Looker/Tableau |
| 4 | "Data Lakehouse Migration: Hadoop Hive → Iceberg on S3" | Migration strategy, Iceberg table format, catalog migration (Hive Metastore → AWS Glue Catalog), incremental migration, rollback plan, performance benchmarking | 8-10 tuần | Apache Iceberg, Spark, AWS EMR/Glue, Trino/Athena, dbt, Terraform |
| 5 | "Feature Store cho ML Platform" | Feature engineering pipeline, offline/online serving, point-in-time correctness, feature registry, integration với ML training pipeline | 8-10 tuần | Spark, Feast/Tecton, Redis/DynamoDB (online store), Kafka, Python, Airflow |
