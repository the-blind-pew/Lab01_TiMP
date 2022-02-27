# Lab01_TiMP

1.Скачиваем библиотеку boost c помощью wget 
$wget -P /Downloads https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz

2.Разархивируем boost в директорию ~/boost_1_69_0 
$tar -C ~/ -x ~/Downloads/boost_1_69_0.tar.gz

3.Подсчёт файлов в директории ~/boost_1_69_0/ не включая вложенные директории 
$tree boost_1_69_0 -L 1
6 directories, 12 files

4.Подсчёт файлов в директории ~/boost_1_69_0/ включая вложенные директории (скрытые тоже считаем, на всякий случай)
$tree boost_1_69_0 -a 
5637 directories, 61191 files

5.Подсчёт кол-ва заголовочныйх файлов и файлов .cpp, подсчёт всех остальных файлов 
$tree boost_1_69_0 -P "*.cpp|*.hpp"
6284 directories, 28686 files

$tree boost_1_69_0 -I "*.cpp|*.hpp"
5637 directories, 32505 files 

6.Полный путь до файла any.hpp внутри библиотеки boots 
$tree boost_1_69_0 -f -P "*.hpp"

7.Вывод в консоль файлов, где упомянается boost::asio
$grep -rl "boost::asio" ~/boost_1_69_0

8.Компиляция boost
$cd boost_1_69_0
$./bootstrap.sh
$./b2

9.Перенос всех скомпилированных библиотек в директорию ~/boost-libs
$mv stage/lib ~/boost-libs

10.Подсчёт размера каждого файла директории
$tree -s boost-libs

11.Вывод 10-ти самых "тяжёлых"
$ls boot-libs/lib -s -S
