## Python | ctypes <img width="30" height="30" alt="image" src="https://github.com/user-attachments/assets/4dd8fa6b-cdfd-4087-960a-4a2fbb8c8590" />

ctypes  - это библиотека внешних функций для Python. Она предоставляет типы данных, совместимые с C, и позволяет вызывать функции из библиотек DLL или общих библиотек. Ее можно использовать для перевода этих библиотек в чистый Python.

•ㅤКрч, вы можете написать список функций(библиотеку), потом юзать ее в python. ctypes работает только с С, к сожалению :(

-------------

### создание проекта / конфигурация (Release + dll)

Я буду использовать Visual Studio от Microsoft для крафта dll. Для начала нужно создать пустой с++ проект, потом в проекте создать cpp и header файлы, затем выбрать режим сборки Release. Так, почти все готово. Осталась выбрать конфигурацию. Чтобы выбрать конфигурацию, перейдите в свойства проекта -> Общие -> Тип конфигурации -> Динамическая библиотека(.dll).

##### Release + cpp/header:

<img width="1280" height="471" alt="image" src="https://github.com/user-attachments/assets/d42e7c89-7cd5-489d-bb22-18604f48bfaf" />

##### dll: 

<img width="1280" height="471" alt="image" src="https://github.com/user-attachments/assets/eda18678-4df4-4b92-90aa-8a6714dc5300" />

------------

### Создание функции

Наша функция должна выглядеть так: extern "C" __declspec(dllexport) тип данных название(тип аргумента название аргумента).

##### cpp:

<img width="929" height="315" alt="image" src="https://github.com/user-attachments/assets/328d9e53-4aca-408c-865a-832f2f42cb94" />

В header файле чуть меняется способ определения. Мы не пишем название аргумента, пишем только тип данных, который принимает аргумент + нет логики.

##### header:

<img width="929" height="315" alt="image" src="https://github.com/user-attachments/assets/4900fdea-a2eb-423e-8486-92c2a45a29f6" />

Теперь можно собирать проект))

----------------------

чет питон не хочет хавать string из ++

крч, яп хуйни работает только с типами данных С + яп хуйни не работает с классами С++

обертка классов или func: 

https://share.google/8ZaskWwMaCYn2c7Ak

https://share.google/ilvSWJxblaWJ0DAmC

https://share.google/6NRK6RMhfQpVGwRdD

крч, я написал func для примера (С)
