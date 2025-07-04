# 🏗️ .NET Clean Architecture Template

Готовый к использованию шаблон для создания микросервисов на .NET с архитектурой Clean Architecture.

## 📋 Что создает шаблон

При использовании команды `dotnet new Capi -n MyProject` создается структура:

```bash
MyProject/
├── README.md                        # Инструкции проекта
├── MyProject.API/                   # Web API слой
├── MyProject.Application/           # Бизнес-логика
├── MyProject.Core/                  # Доменные модели
└── MyProject.Infrastructure/        # Данные и внешние сервисы
```

## 🚀 Быстрый старт

### 1. Добавить источник GitHub Packages

Создайте **[Personal Access Token](https://github.com/settings/tokens/new)** на GitHub с правами:    
- `repo` Full control of private repositories
- `read:packages` и выполните:

```bash
dotnet nuget add source https://nuget.pkg.github.com/iksergey/index.json \
  --name github-iksergey \
  --username YOUR_GITHUB_USERNAME \
  --password YOUR_PERSONAL_ACCESS_TOKEN \
  --store-password-in-clear-text
```

### 2. Установить шаблон

```bash
dotnet new install iksergey.cleanarchitecture.template
```

### 3. Использовать шаблон

```bash
# Создать новый проект
dotnet new Capi -n MyMicroservice

# Перейти в проект и запустить
cd MyMicroservice
dotnet build
dotnet run --project MyMicroservice.API
```

## 🛠️ Управление шаблоном

### Проверить установку
```bash
dotnet new list
```

### Обновить шаблон
```bash
dotnet new install iksergey.cleanarchitecture.template --force
```

### Удалить шаблон
```bash
dotnet new uninstall iksergey.cleanarchitecture.template
```

### Удалить источник
```bash
dotnet nuget remove source github-iksergey
```


## 📚 Дополнительные команды

```bash
# Посмотреть все источники NuGet
dotnet nuget list source
```

---

## 📦 Публикация новых версий (для автора)

### 1. Внести изменения в шаблон
- Отредактируйте файлы в `working/content/Capi/`
- Обновите `PackageVersion` в `Template.csproj`

### 2. Закоммитить и создать тег

```bash
git add .
git commit -m "Update template: добавлена новая функциональность"
git push origin main

# Создать и запушить тег версии
git tag v1.0.0
git push origin v1.0.0
```

### 3. Автоматическая публикация
GitHub Actions автоматически опубликует пакет в GitHub Packages при создании тега.

Проверить публикацию: **Actions** → статус workflow, **Packages** → новая версия.

## 🔧 Локальная разработка шаблона

```bash
# Клонировать репозиторий
git clone https://github.com/iksergey/dotnet-clean-architecture-template.git
cd dotnet-clean-architecture-template

# Установить локально для тестирования
cd working
dotnet new install .

# Тестировать изменения
dotnet new Capi -n TestProject

# Удалить локальную версию
dotnet new uninstall "/полный/путь/к/working"
```

### Sergei Kamianetskii

**GitHub:** [@iksergey](https://github.com/iksergey)
