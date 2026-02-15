# Episode #89: DevOps Дайджест 89

## Introduction
Привет, дорогие слушатели! С вами DevOps Kitchen Talks, и это 89-й выпуск нашего дайджеста. Сегодня мы обсудим сравнение топовых DevOps-платформ 2025 года, преимущества Cilium с eBPF на bare metal и миграцию с Terraform на OpenTofu.

## News

### 1. Top 10 DevOps Platforms in 2025: GitLab CI/CD vs GitHub Actions vs CircleCI vs Devtron
Обзор десяти лучших DevOps-платформ 2025 года, которые интегрируют infrastructure as code, сканирование безопасности и оркестрацию релизов.

**Link:** https://medium.com/@yashbatra11111/top-10-devops-platforms-in-2025-gitlab-ci-cd-vs-github-actions-vs-circleci-vs-devtron-2afb3d4e921a

**Talking Points:**
- Какие критерии наиболее важны при выборе CI/CD платформы в 2025 году: интеграция с IaC, встроенная безопасность или удобство оркестрации релизов?
- GitHub Actions vs GitLab CI/CD: как изменился баланс сил между этими платформами, и какие сценарии использования лучше подходят для каждой из них?
- Появление новых игроков вроде Devtron и Spacelift: какие инновации они привносят на рынок DevOps-платформ и стоит ли рассматривать их как альтернативу классическим решениям?

### 2. Why Running Cilium with eBPF on Bare Metal Outperforms Virtualized Overlay Networks
Анализ производительности Cilium с eBPF на bare metal в сравнении с виртуализированными overlay-сетями.

**Link:** https://openmetal.io/resources/blog/why-running-cilium-with-ebpf-on-bare-metal-outperforms-virtualized-overlay-networks

**Talking Points:**
- Устранение двойной инкапсуляции: насколько критична проблема overhead в виртуализированных облаках и в каких сценариях это становится узким местом?
- Конкретные цифры производительности: снижение задержек на 100-300 мкс и экономия 5-15% CPU — для каких типов приложений эти улучшения будут наиболее заметны?
- Экономика bare metal vs облако: устранение расходов на egress-трафик и использование Jumbo Frames — достаточно ли этих преимуществ для возврата к bare metal инфраструктуре?

### 3. From Terraform to OpenTofu: A Migration Guide
Руководство по миграции с Terraform на OpenTofu — открытый форк с лицензией MPL 2.0 под управлением Linux Foundation.

**Link:** https://www.stackguardian.io/post/from-terraform-to-opentofu-a-migration-guide

**Talking Points:**
- Обратная совместимость с Terraform до версии 1.6: насколько безболезненной будет миграция для существующих проектов и какие подводные камни могут возникнуть?
- Новые возможности OpenTofu: шифрование state-файлов, переменные в backend-конфигурациях и for_each для провайдеров — какие из этих фич наиболее востребованы в реальных проектах?
- Стратегия миграции: стоит ли переходить на OpenTofu прямо сейчас или лучше подождать большей зрелости проекта, учитывая управление со стороны Linux Foundation?

## Conclusion
Спасибо, что были с нами в этом выпуске! Подписывайтесь на наш подкаст, делитесь с коллегами и до встречи в следующем дайджесте!