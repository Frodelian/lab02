# lab02
## Part I
### Задание №1 
### Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
```
https://github.com/Frodelian/lab02
```
### Задание №2
#### Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
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
### Задание №3
#### Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;
```
cat > "Hello_world.cpp" << EOF
#include <iostream>

using namespace std;
int main(int argc, char** argv){
 cout << "Hello world" << endl;
}
EOF
```
### Задание №4
#### Добавьте этот файл в локальную копию репозитория.
```
git add "Hello_world.cpp"
```
### Задание №5
#### Закоммитьте изменения с осмысленным сообщением.
```
git commit -m "Added new cpp file"
```
### Задание №6
#### Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.
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
### Задание №7
#### Почему не надо добавлять файл повторно git add?
```
git commit -a -m "Changed cpp file"
```
### Задание №8
#### Запуште изменения в удалёный репозиторий.
```
git push -u origin master
```
### Задание №9
#### Проверьте, что история коммитов доступна в удалёный репозитории.
```
История коммитов доступна в удалёном репозитории
```
## Part II
### Задание №1 
### В локальной копии репозитория создайте локальную ветку patch1.
```
git checkout -b patch1
```
### Задание №2
### Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;.
```
edit "Hello_world.cpp"
#include <iostream>
#include <string>
 
int main(int argc, char** argv){
 string name;
 std::cin >> name;
 std::cout << "Hello world from " << name << std::endl;
}
```
### Задание №3 
### commit, push локальную ветку в удалённый репозиторий.
```
git commit -a -m "Fixed cpp file"
git push -u origin patch1
```
### Задание №4 
### Проверьте, что ветка patch1 доступна в удалёный репозитории.
```
Ветка patch1 доступна в удалённом репозитории
```
### Задание №5 
### Создайте pull-request patch1 -> master.
```
Создадим pull-request patch1 -> master
```
### Задание №6 
### В локальной копии в ветке patch1 добавьте в исходный код комментарии.
```
edit "Hello_world.cpp"
#include <iostream>
#include <string>
 
int main(int argc, char** argv){
 string name; // User name
 std::cin >> name; // Input user name
 std::cout << "Hello world from " << name << std::endl;
} 
```
### Задание №7 
### commit, push.
```
git commit -a -m "Added comments"
git push -u origin patch1

```
### Задание №8 
### Проверьте, что новые изменения есть в созданном на шаге 5 pull-request
```
Новые изменения есть в созданном на шаге 5 pull-request
```
### Задание №9 
### В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.
```
В удалённом репозитории выполняем слияние PR patch1 -> master и удаляем ветку patch1 в удаленном репозитории.
```
### Задание №10 
### Локально выполните pull.
```
git pull origin
```
### Задание №11
### С помощью команды git log просмотрите историю в локальной версии ветки master.
```
git log
```
### Задание №12
### Удалите локальную ветку patch1.
```
git branch -D patch1
```
## Part III
### Задание №1 
### Создайте новую локальную ветку patch2.
```
git checkout -b patch2
```
### Задание №2
### Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.
```
clang-format -i -style=Mozilla "Hello_world.cpp"
```
### Задание №3
### commit, push, создайте pull-request patch2 -> master.
```
git commit -a -m "Changed code style in cpp file"
git push -u origin patch2
```
### Задание №4
### В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.
```
В ветке master в удаленном репозитории изменяем комментарии

#include <iostream>
#include <string>
 
int main(int argc, char** argv){
 string name; // User n.
 std::cin >> name; // Ввод данных
 std::cout << "Hello world from " << name << std::endl;
}  
```
### Задание №5
### Убедитесь, что в pull-request появились конфликтны.
```
Убеждаемся, что в pull-request появились конфликтны.
```
### Задание №6
### Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.
```
git pull origin master
git rebase master
edit "Hello_world.cpp"
git commit -a -m "Update Hello world.cpp"
git rebase --continue
```
### Задание №7
### Сделайте force push в ветку patch2
```
git push -f origin patch2
```
### Задание №8
### Убедитель, что в pull-request пропали конфликтны.
```
Убеждаемся, что в pull-request пропали конфликтны.
```
### Задание №9
### Вмержите pull-request patch2 -> master.
```
Выполняем merge pull-request patch2 -> master
```



