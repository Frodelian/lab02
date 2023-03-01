# lab02
## Task 1
###Задание №1 
Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
```
https://github.com/Frodelian/lab02
```
###Задание №2
Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
```
mkdir lab02
cd lab02
echo "# lab02" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/Frodelian/lab02
git push -u origin master
```
###Задание №3
Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;
```
cat > "Hello_world.cpp" << EOF
#include <iostream>

using namespace std;
int main(int argc, char** argv){
 cout << "Hello world" << endl;
}
EOF
```
###Задание №4
Добавьте этот файл в локальную копию репозитория.
```
git add "Hello_world.cpp"
```
###Задание №5
Закоммитьте изменения с осмысленным сообщением.
```
git commit -m "Added new cpp file"
```
###Задание №6
Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.
```
alias edit=nano
edit "Hello_world.cpp"
 #include <iostream>
 #include <string>
 
 using namespace std;
 int main(int argc, char** argv){
  string name;
  cin >> name;
  cout << "Hello world from " << name << endl;
 }
```
###Задание №7
Почему не надо добавлять файл повторно git add?
```
git commit -a -m "Changed cpp file"
```
Задание №8
Запуште изменения в удалёный репозиторий.
```
git push -u origin master
```
###Задание №9
Проверьте, что история коммитов доступна в удалёный репозитории.
```
История коммитов доступна в удалёном репозитории
```


