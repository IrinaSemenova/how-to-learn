# Научиться учиться
____
Проект демонстрирует основы верстки HTML-страницы с использованием расширенных возможностей HTML и CSS, правил позиционирования элементов, трансформаций и анимации, а также интегрирования видео-контента со сторонних сервисов через API.
____

__1. В первой части проектной работы__ былы реализованы следующие блоки и секции:
1. Блок __Header__ - шапка сайта с основным заголовком, логотипом и изображениями;
2. Блок __Content__:
    - секция _Description_ - текстовая секция;
    - секция _Digits_ - секция с заголовком и списком;
    - секция _Feynman_ - секция с заголовком, изображениями и ссылкой на другую страницу;
    - секция _Kaufman_ - секция с заголовком, изображением и нумерованным списком;
3. Блок __Footer__ - подвал сайта с логотипом, списком ссылок на сторонние ресурсы;

Для реализации были использованы следующие _основные инструменты и технологии_:
  - стандартные блочные элементы;
  - флексбокс-верстка с созданием флекс-контейнеров с несколькими элементами;
  - к флекс-элементам были пременены правила порядка отображения, распределение пустот, выравнивания и переноса элементов.
  Пример флекс-контейнера:
```
css
  .header {
  height: 100vh;
  min-height: 600px;
  max-height: 756px;
  background-color:#f2f2f2;
  display: flex;
  position: relative;
  align-items: center;
  flex-wrap: wrap;
  overflow:hidden;
}
```
  - были пременены различные виды позиционирования элементов во флекс-контейнере. Пример абсолютного позиционирования элементов:
```
css
  .header__square-pic {
  height: 568px;
  width: 568px;
  background-color: #2f80ed;
  position: absolute;
  right: 0;
  top: 64px;
}
```
  - использованы z-index для управления эффектом наложения элементов друг на друга. Пример z-index:
```
css
  .header__main-illustation {
  width: 765px;
  height: 608px;
  position: absolute;
  bottom: 0;
  right: 0;
  z-index: 1;
}
```
  - в коде использованы списки для удобства пользования страницей слабовидящими и поисковыми системами.
  Пример применения списков:
```
html
  <ul class="table">
          <li class="table__cell">
            <h3 class="table__heading">86 миллиардов</h3>
            <p class="table__text">Число нейронов в мозге человека</p>
          </li>
          ...
  </ul>
```
  - для всех картинок были добавлены альтернативный текст в случае некорректности загрузки изображения. Пример:
```
html
  <img class="header__main-illustation" src="./images/header-image.png" alt="Картинка">
```
  - были использования псевдоклассы для определения правил поведения ряда элементов. Пример использования псевдокласса для сброса отступа у последних элементов:
```
css
  .table__text:not(:last-child) {
  margin-top: 0;
}
```
  - для написания кода применена БЭМ-методология в наименовании блоков, элементов, модификаторов и их значений. Пример использования БЭМ:
```
html
  <h2 class="section-title section-title_theme_dark">Принципы обучения</h2>
```

__2. Во второй части проектной работы__ были внесены изменения в порядок текущих блоков, а также добавлены новые блоки и секции:
1. Блок __Header__ - добавлена анимация для изображения, скорректирована ссылка;
2. Блок __Content__:
    - секция _Description_ - без изменений;
    - секция _Techniques_ - **новая секция** со списком и изображениями;
    - секция _Video_ - **новая секция** с видео;
    - секция _Oakley_ - **новая секция** с текстом;
    - секция _Feynman_ - скорректирована ссылка;
    - секция _Digits_ - без изменений;
    - секция _Khan_ - **новая секция с текстом, с изображением и ссылкой;
    - секция _Kaufman_ - добавлена анимация для изображения;
    - секция _Resources_ - новая секция с заголовком и логотипами;
3. Блок __Footer__ - скорректированы ссылки;

Для реализации второй части проекта были использованы следующие _основные инструменты и технологии_:
  - была создана файловая структура CSS по методолгии БЭМ;
  - dсе ссылки на странице при наведении мыши становятся немного прозрачными, благодаря свойствам opacity и transition:
```
сss
  .header__link {
  color: #2f80ed;
  text-decoration: none;
  opacity: 1;
}

.header__link:hover {
  opacity: 0.5;
  transition: 0,5s;
}
```
  - добавлена анимация для геометрических фигур в блоке Header и секции Kaufman блока Content. Анимация реализованы с помощью keyframes:
```
сss
  @keyframes rotation {
  from {
      transform: rotate(0deg);
  }
  to {
      transform: rotate(360deg);
  }
}
  .rotation__kaufman {
  animation: rotation 20s infinite;
  }
```
  - изображениям в секции Techniques блока Content была задана круглая форма с помощью свойства border-radius со значением 50%;
  - с помощью iframe в секцию Video блока Content было добавлено два видеоролика:
```
html
  <iframe class="video__iframe" width="515" height="316" src="https://www.youtube.com/embed/5MgBikgcWnY" allowfullscreen>
  </iframe>
```
  - для изображения в секции Khan блока Content были использованы свойства object-fit и object-fit, чтобы вписать картинку в установленные размеры блока:
```
сss
  .khan__book-pic {
  width: 620px;
  height: 608px;
  margin-right: 48px;
  padding: 0;
  object-fit: cover;
  object-fit: left top;
}
```
____
__Дальнейшие планы по доработке проекта:__

1. подключить другие шрифты;
2. добавить другие образовательные видео;
3. проверить код на кроссбраузерность и дописать все вендорные префиксы;
4. задизайнить форму, через которую пользователи смогут отправить вам комментарий.
