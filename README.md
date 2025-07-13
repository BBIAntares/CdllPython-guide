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

### внедрение Dll в Pyhon

После всех действий переходим в папку с проектом.

<img width="1020" height="266" alt="image" src="https://github.com/user-attachments/assets/18f3a5df-dbce-4476-ab2b-ec334267b6b7" />

Идем по этому пути: x64 - Release - название проекта. dll (в моем случае: pyLib. dll).

<img width="1020" height="266" alt="image" src="https://github.com/user-attachments/assets/988080f5-77ec-4d0c-8126-1fbd51f3eb72" />

Для работы с python я буду использовать PyCharm. Создаем проект в PyCharm, копируем в папку проекта нашу dll.

<img width="603" height="316" alt="image" src="https://github.com/user-attachments/assets/034bc70a-d4ca-4317-8409-c51adb597dfc" />

Портируем библиотеку +  создаем переменную, которая принимает путь до dll.

<img width="1020" height="266" alt="image" src="https://github.com/user-attachments/assets/b9701b1d-62f3-43b0-84e8-81ca36169bbc" />

вывод в терминал: print(название переменной.название функции(аргумент)). Название функции можно посмотреть в проекте visual studio.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fb2d8aa6-4abc-40ee-9b7c-b1224795d9a0" />


чет питон не хочет хавать string из ++

крч, яп хуйни работает только с типами данных С + яп хуйни не работает с классами С++

обертка классов или func: 

https://share.google/8ZaskWwMaCYn2c7Ak

https://share.google/ilvSWJxblaWJ0DAmC

https://share.google/6NRK6RMhfQpVGwRdD

крч, я написал func для примера (С)
