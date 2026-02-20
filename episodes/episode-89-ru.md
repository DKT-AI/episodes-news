# Выпуск #89: DevOps Дайджест 89

## Вступление
Привет, друзья! С вами DevOps Kitchen Talks, выпуск #89. Сегодня обсудим производительность Cilium на bare metal, массовую миграцию с Terraform на OpenTofu и сравним топовые DevOps-платформы 2025 года.

## Новости

### 1. Why Running Cilium with eBPF on Bare Metal Outperforms Virtualized Overlay Networks
Cilium с eBPF на bare metal OpenMetal превосходит виртуализированные облака за счёт устранения двойной инкапсуляции. Прямая маршрутизация L2, Jumbo Frames (MTU 9000) и 20 Gbps снижают задержки на 100-300 мкс, экономят 5-15% CPU и устраняют расходы на egress-трафик.

**Ссылка:** https://openmetal.io/resources/blog/why-running-cilium-with-ebpf-on-bare-metal-outperforms-virtualized-overlay-networks

**Тезисы для обсуждения:**
- Двойная инкапсуляция в виртуализированных облаках создаёт значительный overhead — как это влияет на latency-sensitive приложения и стоит ли игра свеч при переходе на bare metal?
- Экономия 5-15% CPU и устранение egress-трафика звучит привлекательно, но какова реальная TCO с учётом сложности управления физической инфраструктурой?
- Jumbo Frames с MTU 9000 требуют поддержки всей сетевой цепочки — насколько это реалистично в гибридных и мультиоблачных сценариях?

### 2. Terraform to OpenTofu Migration Guide 2025 | ControlMonkey
Миграция с Terraform на OpenTofu для версий ниже 1.6 проста: замените команду `terraform` на `tofu`. Выполните `tofu init -upgrade` и `tofu apply`. Важно: избегайте прямых ссылок на реестр HashiCorp, используйте короткие имена провайдеров. Сложность возникает при масштабировании на сотни стеков.

**Ссылка:** https://controlmonkey.io/blog/opentofu-migration

**Тезисы для обсуждения:**
- Миграция выглядит тривиальной для небольших проектов, но что делать с сотнями стеков, CI/CD пайплайнами и зависимостями от Terraform Cloud?
- Прямые ссылки на реестр HashiCorp могут сломать миграцию — насколько распространена эта проблема и есть ли автоматизированные инструменты для рефакторинга?
- Стоит ли мигрировать сейчас или подождать большей зрелости экосистемы OpenTofu и инструментов для enterprise-сценариев?

### 3. From Terraform to OpenTofu: A Migration Guide | Blog | StackGuardian
OpenTofu — форк Terraform 1.5.x с лицензией MPL 2.0, управляемый Linux Foundation. Обеспечивает полную обратную совместимость с Terraform до версии 1.6, включает шифрование state-файлов, поддержку переменных в backend-конфигурациях и for_each для провайдеров. Миграция требует обновления кода и тестирования.

**Ссылка:** https://www.stackguardian.io/post/from-terraform-to-opentofu-a-migration-guide

**Тезисы для обсуждения:**
- Шифрование state-файлов и переменные в backend — это киллер-фичи, которых не хватало в Terraform, или просто догоняющее развитие?
- Обратная совместимость до версии 1.6 звучит хорошо, но что происходит с новыми фичами Terraform 1.7+ — останется ли OpenTofu актуальным?
- Linux Foundation как управляющая организация даёт больше доверия, чем HashiCorp с BSL лицензией — достаточно ли этого для массового перехода enterprise-клиентов?

### 4. Top 10 DevOps Platforms in 2025: GitLab CI/CD vs GitHub Actions vs CircleCI vs Devtron
В 2025 году лучшие DevOps-платформы интегрируют infrastructure as code, сканирование безопасности и оркестрацию релизов. Статья сравнивает GitLab CI/CD, GitHub Actions, CircleCI, Devtron, Jenkins, Azure DevOps, Spacelift, Octopus Deploy, Harness и Buddy для выбора оптимального CI/CD решения.

**Ссылка:** https://medium.com/@yashbatra11111/top-10-devops-platforms-in-2025-gitlab-ci-cd-vs-github-actions-vs-circleci-vs-devtron-2afb3d4e921a

**Тезисы для обсуждения:**
- GitHub Actions доминирует благодаря интеграции с экосистемой GitHub, но достаточно ли этого для сложных enterprise-сценариев с compliance и аудитом?
- Новые платформы типа Devtron и Spacelift фокусируются на Kubernetes и IaC — это будущее DevOps или нишевые решения для специфичных задач?
- Jenkins всё ещё в топ-10 в 2025 году — это инерция legacy-проектов или платформа действительно эволюционировала и остаётся конкурентоспособной?

### 5. CI/CD Pipeline Guide: 2025 DevOps Automation Strategies
Современная CI/CD-конвейер автоматизирует сборку, тестирование и развертывание приложений. Популярные инструменты: Jenkins, GitHub Actions, GitLab CI/CD, Azure DevOps. Лучшие практики включают модульные конвейеры для микросервисов, интеграцию безопасности и непрерывную обратную связь.

**Ссылка:** https://mantraideas.com/cicd-pipeline-implementation-guide-2025

**Тезисы для обсуждения:**
- Модульные конвейеры для микросервисов звучат логично, но как избежать explosion сложности при управлении десятками независимых пайплайнов?
- Shift-left security и интеграция сканирования в CI/CD стали стандартом — какие инструменты реально работают без false positives и замедления пайплайнов?
- Непрерывная обратная связь критична для DevOps-культуры — какие метрики и инструменты observability должны быть встроены в современный CI/CD?

## Заключение
Это был DevOps Kitchen Talks, выпуск #89. Спасибо, что были с нами — подписывайтесь, делитесь с коллегами и до встречи в следующем выпуске!