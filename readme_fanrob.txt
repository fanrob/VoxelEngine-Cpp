Установка (мой текущий опыт, Windows 10 x64, путь к проекту: e:\proj\voxel):

Поставил git, Visual Studio 2022(всё, что касается с++), CMake
склонировал с github сам VoxelEngine-cpp

Запустил cmake (как в инструкции к VoxelEngine: cmake -DCMAKE_BUILD_TYPE=Release -DVOXELENGINE_BUILD_WINDOWS_VCPKG=ON ..)
При первом запуске CMake должен скачать vcpkg c git`a сам
Он должен быть в каталоге e:\proj\voxel\VoxelEngine-Cpp\

Затем в каталоге vcpkg запустил .\bootstrap-vcpkg.bat для установки vcpkg

В Path добавил:
c:\Program Files\Microsoft Visual Studio\2022\Enterprise\VC\Tools\MSVC\14.36.32532\bin\Hostx64\x64\
E:\progs\CMake\bin
e:\proj\voxel\vcpkg\
e:\proj\voxel\VoxelEngine-Cpp\vcpkg_installed\x64-windows\

запустил "vcpkg install"

Скопировал из e:\proj\voxel\VoxelEngine-Cpp\vcpkg_installed\x64-windows\lib\
в c:\Program Files (x86)\libpng\lib\ 
libpng16.lib

скопировал папку e:\proj\voxel\VoxelEngine-Cpp\vcpkg_installed\x64-windows\include и *\lib
в e:\proj\voxel\VoxelEngine-Cpp\vcpkg\packages\luajit_x64-windows\
 (VS2022 искал их hpp по luajit там почему-то)

Снова запустил cmake (как в инструкции к VoxelEngine, смотри выше)

Всё равно всё вылетело нафиг. Зато в build появился проект для VS2022

Открыл файл проекта, из VS2022 собрал проект (Debug), должен собратся успешно

скачал либу libcurl-d.dll и glew32d.dll (нашел неотладочные версии, пришлось пока релизные переименовать)
скачать игру версии 0.24 c https://github.com/MihailRis/VoxelEngine-Cpp/releases/download/v0.24.1/voxelcore.0.24.1_win64.zip
распаковал
скопировал папку res (старую от 0.24 версии переименовал)
скопировал exe
Готово, можно играть

