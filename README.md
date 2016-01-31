# Go Project Structure

* Structure
  ```
  <calcproj>
  ├─<src>
    ├─<calc>
      ├─calc.go
    ├─<simplemath>
      ├─add.go
      ├─add_test.go
      ├─sqrt.go
      ├─sqrt_test.go
    ├─<bin>
  ├─<pkg>＃包将被安装到此处
  ```

* 为了能够构建这个工程，需要先把这个工程的根目录加入到环境变量GOPATH中。假设calcproj目录位于~/goyard下，则应编辑~/.bashrc文件，并添加下面这行代码：
  * export GOPATH=~/goyard/calcproj
  * 然后执行以下命令应用该设置：$ source ~/.bashrc, GOPATH和PATH环境变量一样，也可以接受多个路径，并且路径和路径之间用冒号分割。
* 把生成的可执行文件放到calcproj/bin目录中
  ```
  $ cd ~/goyard/calcproj
  $ mkdir bin
  $ cd bin
  $ go build calc
  ```
* Run
  ```
  $ ./calc
  USAGE: calc command [arguments] ...
  The commands are:
  addAddition of two values.
  sqrtSquare root of a non-negative value.
  $ ./calc add 2 3
  Result: 5
  $ ./calc sqrt 9
  Result: 3
  ```
* Test
  * 因为已经设置了GOPATH，所以可以在任意目录下执行以下命令：$ go test simplemath
* Debug
  * Println & Printf
  * $ gdb calc
