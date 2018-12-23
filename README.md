[Техническое задание](SPECS.md)

# Архитектура

### Микросервисы:

Перечисление избыточно! Что-то можно потом добавить (под звездочками)

#### Функциональные
- Passport :10004
  + Базовая информация о пользователе
- Marketplace-frontend :10003
  + Node
- Gate (собирает воедино) :10002
  + One gate to rule them all
- Products (Товары) :10000
  + Стандартные CRUD операции с товарами
  + Поиск, фильтрация товаров
- Advisor (крутые алгоритмы здесь!) :10001
  + Подбор похожих и нужных товаров
- *Auth (JWT, позже OAuth2, авторизация)
- *Profile (страница продавца)
- **Social (комментарии, обсуждение, рейтинг, весь юзер контент, видимый всем)
- **Messaging (личные сообщение)
- **Transactions (переводы, возможно объединить с messaging, тк принципиально похожи)

#### Служебные
- Images (хранит картинки, подгружаются)
- **Video (хранит видео, подгружаются)

# Реализация

Под каждый сервис - отдельный репозиторий, потому что они общаются по http и ничем больше не связаны. 

Также вдруг очень сильно захочется потом часть на другом языке/стеке написать.

###### Держим минимум три ветки: master(она же релиз), features (добавлена фича, работает), dev (живой код, чаще не работает)
