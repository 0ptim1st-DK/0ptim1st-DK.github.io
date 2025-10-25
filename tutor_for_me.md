# Инфа для создания новых фреймов карточек
## 🖼️ 1. ОБЛОЖКИ КАРТОЧЕК ПРОЕКТОВ
В объекте `projectsData` замените иконку на картинку:
Было:
```
{
    id: "autocraft",
    title: "AutoCraft AE2",
    description: "Продвинутая система...",
    image: "fas fa-robot",  // ← Font Awesome иконка
    // ...
}
```
Стало:
```
{
    id: "autocraft",
    title: "AutoCraft AE2", 
    description: "Продвинутая система...",
    image: "images/projects/autocraft-cover.jpg",  // ← Путь к картинке
    // ...
}
```
## 🎥 2. ВИДЕО ОБЗОРЫ В ДЕТАЛЬНОМ ОПИСАНИИ
В `detailedDescription` добавьте видео-контейнер:
```
detailedDescription: `
    <p>Полное описание вашего проекта...</p>
    
    <div class="video-container">
        <iframe src="https://www.youtube.com/embed/КОД_ВИДЕО" 
                frameborder="0" allowfullscreen></iframe>
    </div>
    
    <p>Продолжение описания после видео...</p>
`
```
Или локальное видео:
```
detailedDescription: `
    <p>Описание проекта...</p>
    
    <div class="video-container">
        <video controls>
            <source src="videos/autocraft-demo.mp4" type="video/mp4">
            Ваш браузер не поддерживает видео.
        </video>
    </div>
`
```
## 📸 3. СКРИНШОТЫ В ГАЛЕРЕЕ
В `detailedDescription` добавьте галерею:
```
detailedDescription: `
    <p>Описание проекта с возможностями...</p>
    
    <div class="project-screenshots">
        <div class="screenshot-item" 
             onclick="openGallery([
                 'images/projects/autocraft-screen1.jpg',
                 'images/projects/autocraft-screen2.jpg', 
                 'images/projects/autocraft-screen3.jpg'
             ], 0)">
            <img src="images/projects/autocraft-screen1.jpg" alt="Скриншот 1">
        </div>
        <div class="screenshot-item" 
             onclick="openGallery([
                 'images/projects/autocraft-screen1.jpg',
                 'images/projects/autocraft-screen2.jpg',
                 'images/projects/autocraft-screen3.jpg'
             ], 1)">
            <img src="images/projects/autocraft-screen2.jpg" alt="Скриншот 2">
        </div>
        <div class="screenshot-item" 
             onclick="openGallery([
                 'images/projects/autocraft-screen1.jpg',
                 'images/projects/autocraft-screen2.jpg',
                 'images/projects/autocraft-screen3.jpg'
             ], 2)">
            <img src="images/projects/autocraft-screen3.jpg" alt="Скриншот 3">
        </div>
    </div>
`
```
## 📝 4. ПОЛНЫЙ ПРИМЕР ДЛЯ AUTOCRAFT AE2
```
{
    id: "autocraft",
    title: "AutoCraft AE2",
    description: "Продвинутая система автоматизации для Minecraft",
    image: "images/projects/autocraft-cover.jpg",  // ОБЛОЖКА
    technologies: ["Java", "Minecraft", "Forge API", "Automation"],
    links: [
        { url: "https://github.com/0ptim1st-DK/autocraft-ae2", text: "Исходный код", icon: "fab fa-github" },
        { url: "https://github.com/0ptim1st-DK/autocraft-ae2/blob/main/README.md", text: "Документация", icon: "fas fa-book" }
    ],
    detailedDescription: `
        <p>AutoCraft AE2 - это революционный мод для Minecraft, который выводит автоматизацию крафта на совершенно новый уровень.</p>
        
        <div class="video-container">
            <iframe src="https://www.youtube.com/embed/ДЕМО_ВИДЕО" frameborder="0" allowfullscreen></iframe>
        </div>
        
        <div class="project-features">
            <div class="feature">
                <h4><i class="fas fa-bolt"></i> Интеллектуальный крафт</h4>
                <p>Автоматическое распределение задач и оптимизация ресурсов</p>
            </div>
            <div class="feature">
                <h4><i class="fas fa-network-wired"></i> Расширенная логистика</h4>
                <p>Сложные цепочки крафта и умное управление предметами</p>
            </div>
        </div>
        
        <div class="project-screenshots">
            <div class="screenshot-item" 
                 onclick="openGallery([
                     'images/projects/autocraft-ui.jpg',
                     'images/projects/autocraft-crafting.jpg',
                     'images/projects/autocraft-storage.jpg'
                 ], 0)">
                <img src="images/projects/autocraft-ui.jpg" alt="Интерфейс AutoCraft">
            </div>
            <div class="screenshot-item" 
                 onclick="openGallery([
                     'images/projects/autocraft-ui.jpg', 
                     'images/projects/autocraft-crafting.jpg',
                     'images/projects/autocraft-storage.jpg'
                 ], 1)">
                <img src="images/projects/autocraft-crafting.jpg" alt="Процесс крафта">
            </div>
            <div class="screenshot-item" 
                 onclick="openGallery([
                     'images/projects/autocraft-ui.jpg',
                     'images/projects/autocraft-crafting.jpg',
                     'images/projects/autocraft-storage.jpg'
                 ], 2)">
                <img src="images/projects/autocraft-storage.jpg" alt="Система хранения">
            </div>
        </div>
        
        <p>Проект активно развивается и постоянно пополняется новыми функциями!</p>
    `
}
```
## 📁 СТРУКТУРА ФАЙЛОВ:
```
ваш-репозиторий/
├── images/
│   └── projects/
│       ├── autocraft-cover.jpg      # Обложка карточки
│       ├── autocraft-ui.jpg         # Скриншоты для галереи
│       ├── autocraft-crafting.jpg
│       └── autocraft-storage.jpg
└── videos/
    └── autocraft-demo.mp4           # Локальное видео
```
## 🎯 ЧТО ГДЕ ИСПОЛЬЗОВАТЬ:
- 🖼️ Обложки - `image:` в основном объекте проекта
- 🎥 Видео - `<div class="video-container">` в `detailedDescription`
- 📸 Скриншоты - `<div class="project-screenshots">` в `detailedDescription`
- 📊 Диаграммы/схемы - тоже через галерею или прямо в тексте
### Теперь вы можете добавлять медиа в любую часть сайта! 🚀
---

# 🆕 ДОБАВЛЕНИЕ НОВЫХ ПРОЕКТОВ
## 1. В существующую категорию и подкатегорию:
Найдите в JavaScript объект `projectsData` и добавьте в массив `projects`:
```
// Пример: добавить новый проект в Minecraft
subcategories: {
    minecraft: {
        title: "Minecraft", 
        icon: "fas fa-cube",
        projects: [
            // СУЩЕСТВУЮЩИЙ ПРОЕКТ
            {
                id: "autocraft",
                title: "AutoCraft AE2",
                description: "Продвинутая система автоматизации...",
                // ... остальные параметры
            },
            // ⬇️ НОВЫЙ ПРОЕКТ ДОБАВЛЯЕМ ЗДЕСЬ
            {
                id: "new-minecraft-mod",
                title: "Новый Мод для Minecraft",
                description: "Описание нового мода...",
                image: "images/projects/new-mod-cover.jpg",
                technologies: ["Java", "Minecraft", "Fabric"],
                links: [
                    { url: "https://github.com/0ptim1st-DK/new-mod", text: "Исходный код", icon: "fab fa-github" }
                ],
                detailedDescription: `
                    <p>Полное описание нового мода...</p>
                    <div class="project-screenshots">
                        <div class="screenshot-item" 
                             onclick="openGallery(['images/projects/new-mod-screen1.jpg'], 0)">
                            <img src="images/projects/new-mod-screen1.jpg" alt="Скриншот">
                        </div>
                    </div>
                `
            }
        ]
    }
}
```
## 2. В новую подкатегорию:
```
subcategories: {
    minecraft: {
        title: "Minecraft",
        icon: "fas fa-cube",
        projects: [/* существующие проекты */]
    },
    // ⬇️ НОВАЯ ПОДКАТЕГОРИЯ
    newgames: {
        title: "Другие игры", 
        icon: "fas fa-gamepad",
        projects: [
            {
                id: "unity-game",
                title: "Игра на Unity",
                description: "3D игра разработанная на Unity...",
                image: "images/projects/unity-game-cover.jpg",
                technologies: ["C#", "Unity", "3D Graphics"],
                links: [
                    { url: "https://github.com/0ptim1st-DK/unity-game", text: "GitHub", icon: "fab fa-github" }
                ],
                detailedDescription: `<p>Описание Unity игры...</p>`
            }
        ]
    }
}
```
## 3. В новую категорию:
Добавьте новую категорию в объект `projectsData`:
```
const projectsData = {
    games: {
        title: "🎮 Игры",
        icon: "fas fa-gamepad",
        subcategories: {/* существующие */}
    },
    programs: {
        title: "💻 Программы", 
        icon: "fas fa-laptop-code",
        subcategories: {/* существующие */}
    },
    // ⬇️ НОВАЯ КАТЕГОРИЯ
    websites: {
        title: "🌐 Веб-сайты",
        icon: "fas fa-globe",
        subcategories: {
            frontend: {
                title: "Frontend",
                icon: "fab fa-js",
                projects: [
                    {
                        id: "react-app",
                        title: "React Приложение",
                        description: "Современное веб-приложение на React...",
                        image: "images/projects/react-app-cover.jpg",
                        technologies: ["React", "JavaScript", "CSS3"],
                        links: [
                            { url: "https://github.com/0ptim1st-DK/react-app", text: "Код", icon: "fab fa-github" },
                            { url: "https://react-app-demo.netlify.app", text: "Демо", icon: "fas fa-external-link-alt" }
                        ],
                        detailedDescription: `<p>Описание React приложения...</p>`
                    }
                ]
            }
        }
    }
};
```
## 🎨 ШАБЛОНЫ ДЛЯ БЫСТРОГО ДОБАВЛЕНИЯ:
### Шаблон для Python проекта:
```
{
    id: "python-tool",
    title: "Python Утилита",
    description: "Полезная утилита для автоматизации...",
    image: "fab fa-python", // или путь к картинке
    technologies: ["Python", "Automation", "CLI"],
    links: [
        { url: "https://github.com/0ptim1st-DK/python-tool", text: "Исходный код", icon: "fab fa-github" }
    ],
    detailedDescription: `<p>Описание Python утилиты...</p>`
}
```
### Шаблон для мобильного приложения:
```
{
    id: "android-app",
    title: "Android Приложение", 
    description: "Мобильное приложение для Android...",
    image: "fab fa-android",
    technologies: ["Kotlin", "Android", "Material Design"],
    links: [
        { url: "https://github.com/0ptim1st-DK/android-app", text: "GitHub", icon: "fab fa-github" },
        { url: "https://play.google.com/store/apps/details?id=com.yourapp", text: "Google Play", icon: "fab fa-google-play" }
    ],
    detailedDescription: `<p>Описание Android приложения...</p>`
}
```
## ⚠️ ВАЖНЫЕ МОМЕНТЫ:
- Уникальный ID - каждый проект должен иметь уникальный id
- Правильная вложенность - следите за фигурными скобками и запятыми
- Запятые между проектами - после каждого проекта кроме последнего
- Картинки - можно использовать Font Awesome или пути к файлам

## 🔧 ПРОВЕРКА ПРАВИЛЬНОСТИ:
После добавления проверьте:
- ✅ Все фигурные скобки закрыты
- ✅ Запятые между элементами массивов
- ✅ ID уникальные
- ✅ Пути к файлам правильные

## Новые проекты появятся автоматически на странице "Проекты"! 🚀
