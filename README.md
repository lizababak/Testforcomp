# Testforcomp
Тестовое задание
Сценарий
Необходимо разработать систему сбора и просмотра контактов в CRM. Основными
возможностями системы являются быстрый поиск, добавление и удаление контактов из одной
общей страницы.
Требования
1. В задании будут использоваться стандартные объекты Contact, Account, Case. Создавать
новые объекты не нужно.
2. У объекта Contact необходимо добавить новое поле Contact Level (picklist) со значениями
Primary, Secondary, Tertiary.
Визуальная часть (Front End)
Визуальная часть задания представляет из себя Lightning APP (Contact Manager). В этом
APP должен отображаться Lightning main component который должен отображать все
существующие контакты.
Необходимо отобразить следующие поля: Name (link - по клику на запись должен
открываться выбранный контакт), Email, Contact Level (picklist), Account (lookup), Owner
(lookup), Created By (lookup), Created Date. Lookup поля должны отображаться в виде имён
записей - не Id.
Таблица должна поддерживать пагинацию (по 10 контактов на странице) и сортировку по
любому столбцу (по клику на заголовке).
Напротив каждого контакта нужно показать кнопку Del, которая будет удалять контакт из
базы данных.
Также в Lightning main component должно быть поле для поиска контактов по имени
(частичное совпадение по first/last name). И кнопка Search. Результаты поиска должны
отображаться в той же таблице и должны показывать те же столбцы.
Кроме этого необходимо сделать кнопку ‘New Contact’, которая откроет модальное окно
(new Lightning component), где можно будет ввести First Name, Last Name *, Email *, Contact
Level, Account и нажать Save или Cancel.
Серверная часть (Back End)
При создании нового контакта автоматически должен создаваться Case при помощи
триггера. Case должен привязываться к новому контакту. Если контакт ссылается на аккаунт,
тогда новый Case также должен ссылаться на этот аккаунт.
Поле Status у нового Case должно принимать значение ‘Working’, а поле Case Origin
должно принимать значение ‘New Contact’.
Поле Owner у Case должен быть таким же как Owner у аккаунта, на которого ссылается
контакт. Также поле Priority у нового Case должно зависеть от того, какое значение было выбрано
Конфиденциально! Данное задание предназначено для индивидуального выполнения. Не подлежит
копированию, размножению и передаче третьим лицам!
в поле Contact Level у контакта. Если оно было Primary тогда Priority = ‘High’, если оно было
‘Secondary’ тогда Priority = ‘Medium’, если оно было ‘Tertiary’ тогда Priority = ‘Low’.
Весь код классов и триггеров должен быть покрыт юнит тестами. Тесты должны не только
покрывать код, но также и тестировать правильность логики ваших методов.
