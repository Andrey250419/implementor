Требуется реализовать `Implementor` – программу, которая будет генерировать
 компилируемые реализации данных интерфейсов или абстрактных классов.

### Требования:

* Ваш класс должен реализовывать интерфейс `Implementor`
  и удовлетворять его спецификации (см. комментарии к этому интерфейсу). 
  Заранее хочу попросить прощения за русскоязычные комментарии, надеюсь, вы не сильно расстроитесь.
  Исходники должны быть написаны в кодировке UTF-8.
  Реализация должна находится в пакете `ru.compscicenter.java2017.implementor`
  В репозитории не должно находится ничего, кроме исходников и файлов конфигурации.

* В реализации разрешено пользоваться любыми классами стандартной библиотеки,
  но запрещено подключать сторонние библиотеки.
 
### Процесс сдачи:

* Сдавать задачу нужно также, как и остальные – через SVN. Шаблон решения задачи появился в ветке `trunk`.
    Для того чтобы этот шаблон появился в вашей персональной ветке, нужно сделать знакомую команду `svn merge "^/trunk"`.
    Далее, нужно также, как и в первой задаче обновить файлик `main/resources/build.properties`
    (Почта и класс, который реализует интерфейс `Implementor`)

* Условием сдачи задания являются все пройденные тесты и отсутствие замечаний в `checkstyle`.
  Если вы этого добились, нужно отписаться в комментариях к задаче на сайте
  и указать номер успешного билда (приходит в письме от проверяющей системы).
  Письма системы имеют привычку попадать в спам, так что проверяйте наличие письма везде.
  Также я могу посмотреть глазами ваш код и сказать свои замечания.

* `checkstyle` – программа, которая проверяет соответствие вашего кода
    стандартам оформления и пишет отчет о тех проблемах, которые она смогла заметить.
    Внимание – в письме-отчете не будет ни слова о том, сколько проблем нашла автоматическая проверка кода.
    Вам необходимо самим научится запускать этот инструмент. Программа настроена в виде плагина к `maven`у.
    Все что вам нужно сделать для запуска – запустить цель `checkstyle:check`.
    
    Отчет будет в подобном виде:
    
        [INFO] --- maven-checkstyle-plugin:2.13:check (default-cli) @ multiset ---
        [INFO]
        [INFO] There are 1 checkstyle errors.
        [ERROR] SimpleMultiSet.java[71:28] (whitespace) WhitespaceAround: '{' is not preceded with whitespace.
        [INFO] ------------------------------------------------------------------------
        [INFO] BUILD FAILURE
        
    Соответственно, указано, сколько ошибок оформления, что это за ошибки и удачно ли завершилась проверка или нет.
    Ваша задача получить заветное
    
        [INFO] --- maven-checkstyle-plugin:2.13:check (default-cli) @ multiset ---
        [INFO]
        [INFO] ------------------------------------------------------------------------
        [INFO] BUILD SUCCESS
        
        
*  Также, есть шаблон для написания unit-тестов. Для их написания используется библиотека JUnit.
   Небольшой пример и полезные для тестирования функции 
   есть в классе `ImplementorTest`.
   Если у вас запускаются свои тесты (целью `test`), то должны запускаться и тесты на сервере сборки и тестирования.
  
*  Задание в основном на использование Reflection API, работу с ClassLoader, чуть-чуть на ввод-вывод и на исключения.

*  Все обсуждения стоит вести в [чате](https://cscenter.slack.com/messages/java-17/).
