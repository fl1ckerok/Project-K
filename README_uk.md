[ENG](https://github.com/iamavasya/Project-K/blob/main/README.md) | UKR
# Project-K ⚡

**Project-K** — це застосунок на базі ASP.NET Core, призначений для надання куреням бази даних для управління своїми учасниками, включаючи молодь, виховників, впливових членів та іншу важливу інформацію. 🛠️

## Особливості ✨
- 👥 Додавання, редагування, перегляд та видалення учасників.
- 🔑 Управління користувачами на основі ролей з кастомними ролями.
- 📝 Реєстрація користувачів, автентифікація та призначення ролей.
- ⚙️ Гнучка кодова база для легких модифікацій під конкретні потреби.

## Інсталяція 🖥️
1. Клонуйте репозиторій:  
   `git clone https://github.com/iamavasya/Project-K.git`
2. Завантажте та налаштуйте **MySQL Server** на вашому пристрої.
3. Вкажіть рядок підключення в налаштуванні `DefaultConnection`:  
   `ConnectionString:DefaultConnection`
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=your_database_name;User=root;Password=your_password;"
  },
}
```
4. **Додайте свій API ключ Google Places** в `appsettings.json` під `"ApiSettings"`:  
```json
"ApiSettings": { 
    "ApiKey": "YOUR-KEY" // Replace with your actual API key
}
```
5. Відновіть залежності та зберіть проект:  
```
dotnet restore
dotnet build
```
6. Оновіть базу даних за допомогою міграцій Entity Framework: 
```
dotnet ef database update
```
8. Запустіть застосунок 
```
dotnet run
```

> [!IMPORTANT]
> Переконайтеся, що ви запускаєте всі команди `dotnet` з відповідних каталогів: каталог `.App` для команд застосунку та каталог `.Infrastructure` для оновлень бази даних.

## Функція Автозаповнення 🔍

У проекті ви знайдете `AutocompleteScript.cshtml`, розташований у `Project-K.App/Views/Shared`, який підтягує API з Google Places. Переконайтеся, що ви вставили свій власний API ключ в `appsettings.json` під `"ApiSettings"`.
```cshtml
@* Views/Shared/_AutocompleteScripts.cshtml *@
<script src="https://maps.googleapis.com/maps/api/js?key=@ViewData["ApiKey"]&libraries=places"></script>
```

## Дорожня карта 🗺️

### Поточні функції
- Управління користувачами (додавання, редагування, видалення).
- Створення та призначення ролей.
- Реєстрація та автентифікація користувачів.

### Заплановані функції
- 📋 Таблиця лідерів для визнання користувачів.
- ⭐ Система точкування для залучення учасників.
- 📅 Додавання та управління заходами.
- 📚 Архів для записів учасників.

### Майбутні вдосконалення
- 🔍 Поліпшення архітектури застосунку для масштабованості.
- 🌐 Інтеграція зовнішніх сервісів.
- 🔄 Реалізація Middleware та Repository патернів.

## Вимоги 📦
- .NET Core SDK
- MySQL Server

## Внески та залучення 🤝
Не соромтеся відкривати проблеми або надсилати запити на внесок для вдосконалення проекту

## Ліцензія 📜
Цей проект ліцензовано під ліцензією MIT.
