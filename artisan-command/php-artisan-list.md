
```php
php artisan list
```
-   Chức năng: Hiển thị danh sách tất cả các lệnh Artisan có sẵn trong ứng dụng Laravel của ta.
-   Cấu trúc hiển thị:
    - Nhóm lệnh (ex: make, migrate, db, ...)
-   Lệnh cụ thể trong mỗi nhóm (ex: make:model, db:seed, ...)

- Tương đương với việc chúng ta muốn xem tất cả những gì Artisan có thể làm được.
---
```php
php artisan <command-groups> help
ex:
php artisan make help
php artisan schedule help
...
```
-   Lệnh php artisan <command-group> help
-   Giúp hiển thị danh sách tất cả các lệnh trong một nhóm lệnh cụ thể của Laravel.
-   Ta có thể dùng lệnh này để xem chi tiết các lệnh có sẵn trong các nhóm như make, migrate, queue, v.v.

-   Cấu trúc hiển thị khi chạy php artisan <command-group> help:
    - Nhóm lệnh (ex: make, migrate, db, ...):
    - Đây là các nhóm chức năng, mỗi nhóm chứa các lệnh liên quan đến một tác vụ cụ thể trong ứng dụng Laravel.

-   Lệnh cụ thể trong mỗi nhóm (ex: make:model, db:seed, ...):
-   Là các lệnh chi tiết mà ta có thể thực thi trong từng nhóm.
-   Mỗi lệnh sẽ thực hiện một tác vụ cụ thể.

**Ví dụ 1: ```php artisan make help```:**

**Khi ta chạy ```php artisan make help```, ta sẽ nhận được thông tin về các lệnh trong nhóm make, bao gồm các lệnh tạo các thành phần như controller, model, migration, seeder, v.v.**

-   Cấu trúc hiển thị
```php
Available commands for the "make" namespace:
  make:class                Create a new class
  make:command              Create a new Artisan command
  make:component            Create a new view component class
  make:controller           Create a new controller class
...
```
-   Nhóm lệnh: make
-   Các lệnh trong nhóm: make:controller, make:model, make:migration, v.v...
---

```php
php artisan <command> --help
php artisan make:controller --help
php artisan make:seeder --help
...
```
-   Chức năng của php artisan <command> --help:
-   Ví dụ: Khi ta chạy lệnh như ```php artisan make:controller --help```, nó sẽ hiển thị thông tin chi tiết về cách sử dụng lệnh đó, bao gồm các tùy chọn và tham số có sẵn, cũng như mô tả chức năng của lệnh đó.
-   Cấu trúc hiển thị khi chạy php artisan <command> --help:
-   Tên lệnh: Chỉ rõ lệnh mà ta đang muốn tìm hiểu (ví dụ: make:controller, make:seeder,..).
-   Mô tả lệnh: Mô tả tác dụng của lệnh (ví dụ: "Create a new controller").
-   Cú pháp lệnh: Hiển thị cú pháp cơ bản và các tham số bắt buộc/tùy chọn mà lệnh có thể nhận.
-   Các tùy chọn: Liệt kê các tham số và tùy chọn mà ta có thể sử dụng cùng với lệnh đó.

**Ví dụ 2: ```php artisan make:controller --help```**
-   Khi ta chạy lệnh
```php
php artisan make:controller --help
```
-   Laravel sẽ hiển thị thông tin về lệnh make:controller như sau:
-   Cấu trúc hiển thị:
```php
Usage:
  make:controller <name> [options] [--] 

Arguments:
  name                     The name of the controller

Options:
  -r, --resource           Generate a resource controller (includes CRUD methods)
  -m, --model[=MODEL]      The model that the controller should use
  -a, --api                Generate an API controller (no web middleware)
  -p, --parent[=PARENT]    The parent controller class
  -f, --force              Create the controller even if it already exists
  -h, --help               Display help for the command

Description:
  Create a new controller class.
```

-   Giải thích cấu trúc hiển thị:
-   Usage: Cung cấp cú pháp cơ bản của lệnh make:controller, trong đó <name> là đối số bắt buộc (tên controller mà bạn muốn tạo) và [options] là các tham số tùy chọn bạn có thể sử dụng.
-   Arguments:
-   name: Đây là đối số bắt buộc, bạn phải chỉ định tên controller khi chạy lệnh. Ví dụ: php artisan make:controller MyController.
-   Options:
    -   -r, --resource: Tạo một controller resource (bao gồm các phương thức CRUD cơ bản).

    -   -m, --model[=MODEL]: Chỉ định một model mà controller này sẽ sử dụng.

    -   -a, --api: Tạo một API controller (không có middleware web).

    -   -p, --parent[=PARENT]: Chỉ định controller cha mà controller này sẽ kế thừa.

    -   -f, --force: Tạo controller ngay cả khi nó đã tồn tại.

    -   -h, --help: Hiển thị thông tin trợ giúp cho lệnh.

-   Description: Mô tả chức năng của lệnh, trong trường hợp này là "Create a new controller class." (Tạo một lớp controller mới).
