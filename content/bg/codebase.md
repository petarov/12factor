## I. Кодова база
### Една кодова база следена от софтуер за управление на версиите, много разгръщания

Приложението на дванадесетте фактора винаги използва софутер за управление на версиите, като [Git](http://git-scm.com/), [Mercurial](https://www.mercurial-scm.org/), или [Subversion](http://subversion.apache.org/).  Копието на базата от данни, която следи версиите (ревизиите) се нарича *хранилище на код* или за по-кратко *код репо*.

*Кодова база* е всяко едно репо (в централизиран софтуер за управление на версиите като Subversion), или набор от репота (в децентрализиран софтуер за управление на версиите като Git), които водят началото си от общ първи комит.

![Една кодова база следена от софтуер за управление на версиите, много разгръщания](/images/codebase-deploys.png)

Винаги има съответствие едно към едно между кодовата база и приложението:

* Ако има повече от една кодова база, то тогава става въпрос не за приложение, а за дистрибутирана система. Всеки компонент в една такава система е приложение, което следва предписанията на дванадесетте фактора самостоятелно.
* Множество приложения споделящи един и същ код се счита за нарушение на дванадесетте фактора.  Решението в такъв случай е да се раздели споделения код в библиотеки, които да бъдат използвани посредством [мениджър на зависимостите](./dependencies).

Има само една кодова база за дадено приложение, но пък може да има много разгръщания (deploys) на това приложение.  *Разгръщането* представлява привеждането на приложението в активно работно състояние.  Типични разгръщания са продуктивната среда или една, или повече междинни работни среди.  Допълнително, всеки разработчик има копие на приложението стартирано в дев работната си среда, като това стартиране също бива квалифицирано като разгръщане.

Кодовата база е една и съща при всички разгръщания, макар и версиите при всяко разгръщане да се различават.  Например, един разработчик може да има няколко комита, които все още не са разгърнати в междинната среда или пък междинната среда има комити, които не са разгърнати в продуктивната среда.  Всички среди споделят едина и съща кодова база, като по този начин биват идентифицирани просто като различни разгръщания на едно и също приложение.