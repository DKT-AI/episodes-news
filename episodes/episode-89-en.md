# Episode #89: DevOps Дайджест 89

## Introduction
Привет, друзья! С вами DevOps Kitchen Talks, и это 89-й выпуск нашего дайджеста. Сегодня обсудим производительность Cilium на bare metal, миграцию с Terraform на OpenTofu, а также сравним топовые DevOps-платформы и стратегии автоматизации CI/CD в 2025 году.

## News

### 1. Why Running Cilium with eBPF on Bare Metal Outperforms Virtualized Overlay Networks
Cilium с eBPF на bare metal OpenMetal превосходит виртуализированные облака за счёт устранения двойной инкапсуляции. Прямая маршрутизация L2, Jumbo Frames (MTU 9000) и 20 Gbps снижают задержки на 100-300 мкс, экономят 5-15% CPU и устраняют расходы на egress-трафик.

**Link:** https://openmetal.io/resources/blog/why-running-cilium-with-ebpf-on-bare-metal-outperforms-virtualized-overlay-networks

**Talking Points:**
- Как двойная инкапсуляция в виртуализированных средах влияет на производительность сети и почему bare metal решает эту проблему
- Практические преимущества использования Jumbo Frames с MTU 9000 и прямой L2-маршрутизации для высоконагруженных приложений
- Экономия на egress-трафике и CPU: в каких сценариях переход на bare metal с Cilium наиболее оправдан

### 2. Terraform to OpenTofu Migration Guide 2025 | ControlMonkey
Миграция с Terraform на OpenTofu для версий ниже 1.6 проста: замените команду `terraform` на `tofu`. Выполните `tofu init -upgrade` и `tofu apply`. Важно: избегайте прямых ссылок на реестр HashiCorp, используйте короткие имена провайдеров. Сложность возникает при масштабировании на сотни стеков.

**Link:** https://controlmonkey.io/blog/opentofu-migration

**Talking Points:**
- Насколько действительно проста миграция для небольших проектов и какие подводные камни могут возникнуть с версиями Terraform 1.6+
- Проблемы масштабирования миграции на сотни стеков: автоматизация процесса и управление зависимостями провайдеров
- Стратегии работы с реестром провайдеров: почему важно избегать прямых ссылок на HashiCorp и как правильно настроить альтернативные источники

### 3. From Terraform to OpenTofu: A Migration Guide | Blog | StackGuardian
OpenTofu — форк Terraform 1.5.x с лицензией MPL 2.0, управляемый Linux Foundation. Обеспечивает полную обратную совместимость с Terraform до версии 1.6, включает шифрование state-файлов, поддержку переменных в backend-конфигурациях и for_each для провайдеров.

**Link:** https://www.stackguardian.io/post/from-terraform-to-opentofu-a-migration-guide

**Talking Points:**
- Ключевые новые возможности OpenTofu: шифрование state-файлов и переменные в backend — как это улучшает безопасность и гибкость
- Обратная совместимость до Terraform 1.6: что происходит с проектами на более новых версиях и стоит ли ждать дальнейшего развития OpenTofu
- Роль Linux Foundation в развитии проекта и перспективы открытой экосистемы IaC-инструментов

### 4. Top 10 DevOps Platforms in 2025: GitLab CI/CD vs GitHub Actions vs CircleCI vs Devtron
В 2025 году лучшие DevOps-платформы интегрируют infrastructure as code, сканирование безопасности и оркестрацию релизов. Статья сравнивает GitLab CI/CD, GitHub Actions, CircleCI, Devtron, Jenkins, Azure DevOps, Spacelift, Octopus Deploy, Harness и Buddy для выбора оптимального CI/CD решения.

**Link:** https://medium.com/@yashbatra11111/top-10-devops-platforms-in-2025-gitlab-ci-cd-vs-github-actions-vs-circleci-vs-devtron-2afb3d4e921a

**Talking Points:**
- Критерии выбора DevOps-платформы в 2025: что важнее — интеграция с экосистемой, встроенная безопасность или гибкость настройки
- Сравнение популярных решений: GitHub Actions для простоты, GitLab для полноты функций, или специализированные платформы типа Harness и Devtron
- Тренды интеграции IaC и security scanning непосредственно в CI/CD: как это меняет подход к построению конвейеров

### 5. CI/CD Pipeline Guide: 2025 DevOps Automation Strategies
Современная CI/CD-конвейер автоматизирует сборку, тестирование и развертывание приложений. Популярные инструменты: Jenkins, GitHub Actions, GitLab CI/CD, Azure DevOps. Лучшие практики включают модульные конвейеры для микросервисов, интеграцию безопасности и непрерывную обратную связь.

**Link:** https://mantraideas.com/cicd-pipeline-implementation-guide-2025

**Talking Points:**
- Модульные конвейеры для микросервисной архитектуры: как правильно организовать независимые pipeline и избежать монолитных конфигураций
- Shift-left security: интеграция сканирования уязвимостей и compliance-проверок на ранних этапах CI/CD
- Непрерывная обратная связь и метрики: какие KPI действительно важны для оценки эффективности автоматизации развертывания

## Conclusion
На этом наш 89-й выпуск подходит к концу. Спасибо, что были с нами — следите за новостями DevOps, и до встречи в следующем дайджесте!