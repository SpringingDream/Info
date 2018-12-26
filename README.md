[Техническое задание](SPECS.md)

# Архитектура

### Микросервисы:

Перечисление избыточно! Что-то можно потом добавить (под звездочками)

#### Функциональные
- User History : (marketplace-userhistory)
  + Информация о покупках и изменении рейтинга
- Passport (marketplace-passport)
  + Базовая информация о пользователе
- Marketplace-frontend 
  + React SPA-приложение
- Gate (собирает воедино) 
  + One gate to rule them all
- Products (Товары) (marketplace-products)
  + Стандартные CRUD операции с товарами
  + Поиск, фильтрация товаров
- Adviser (крутые алгоритмы здесь!) (marketplace-adviser)
  + Подбор похожих и нужных товаров
- *Auth (JWT, позже OAuth2, авторизация)
- *Profile (страница продавца)
- **Social (комментарии, обсуждение, рейтинг, весь юзер контент, видимый всем)
- **Messaging (личные сообщения)
- **Transactions (переводы, возможно объединить с messaging, тк принципиально похожи)

#### Служебные
- *Images (хранит картинки, подгружаются)
- **Video (хранит видео, подгружаются)

# Реализация

Под каждый сервис - отдельный репозиторий, потому что они общаются по http и ничем больше не связаны. 

Также вдруг очень сильно захочется потом часть на другом языке/стеке написать.

###### Держим минимум три ветки: master(она же релиз), features (добавлена фича, работает), dev (живой код, чаще не работает)
