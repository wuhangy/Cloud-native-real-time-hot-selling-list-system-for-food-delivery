项目背景与核心价值
设计并实现了一个支撑千万级 DAU 外卖平台的实时热销榜系统，解决传统排行榜计算延迟高（分钟级）、缓存穿透、扩展性差等痛点。系统采用读写分离 + 最终一致性架构，通过 Redis Sorted Set 实现毫秒级排名计算，支持多时间维度（实时/日/周/月/全部）热销排行，并提供高可用（99.95%）、可观测、弹性伸缩的云原生部署方案。单机 QPS 突破 15,000+，P99 延迟 < 50ms。

核心职责与技术实现
主导系统全流程开发，包括架构设计、核心代码编写、性能优化、容器化部署及 CI/CD 流水线搭建。设计缓存旁路 + 写穿透双模式，通过 Redis Pipeline 批量更新，缓存命中率达 92%；优化 N+1 查询，响应时间从 200ms 降至 35ms。基于 Kubernetes 实现滚动更新、HPA 自动扩缩容（2-10 副本）和金丝雀发布，节省 40% 资源成本。集成 Prometheus + Grafana 监控 20+ 核心指标，配置告警规则并对接钉钉实时通知。

项目成果与量化指标
支撑单日 500 万 + 订单量，排行榜更新延迟 < 100ms，全年故障时间 < 4 小时（可用性 99.95%）。数据库 QPS 降低 60%，资源利用率提升 35%。通过 Jenkins Pipeline 实现代码提交到生产部署全自动（5 分钟完成），集成 SonarQube 和 Trivy 保障代码安全。项目已在 GitHub 开源（200+ stars），技术博客阅读量 5000+。
# -HotRank---
【技术栈】
后端：Python Flask + SQLAlchemy + Redis + MySQL + Gunicorn
前端：React 18 + Ant Design + Zustand + Axios + Recharts
容器化：Docker + Kubernetes (K8s) + Docker Compose
编排与部署：K8s (Deployment/Service/Ingress/HPA) + Minikube
CI/CD：Jenkins Pipeline + GitLab CI + SonarQube + Trivy
监控：Prometheus + Grafana + AlertManager + 钉钉告警
数据库：MySQL 8.0 + Redis 7.0 (主从 + 哨兵)
Web服务器：Nginx + Gunicorn
版本控制：Git + GitHub
测试：pytest + Jest + Locust
