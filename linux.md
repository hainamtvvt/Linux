# Linux
## Cấu trúc thư mục trong linux
### 1. Mở đầu

![Capture](https://user-images.githubusercontent.com/63154819/99865410-01ec6080-2bdc-11eb-952a-f7a97ec99516.PNG)

#### 1.1 Root
* Đây là nơi bắt đầu của tất cả các files và thư mục. Đây là thư mục cao cấp nhất trên hệ thống, chứa tất cả các thư mục khác, bao gồm những thư mục con của chúng và mọi file nằm trong đó.
#### 1.2 Bin - Chương trình của người dùng
* Trong chương trình này, chứa các chương trình thực thi được. Các chương trình được dùng chung cho tất cả user trong hệ thống
* Các tập tin thực thi của người dùng. Chứa các file là những lệnh của Linux cho cá nhân người sử dụng hoặc cho tất cả các user. Các lệnh có thể lưu ở dạng nhị phân hoặc là .sh (người dùng có thể chạy được các lệnh như bash hay mkdir, ls,pwd, date....đều cho chúng có trong thư mục này).
#### 1.2 sbin - Chương trình hệ thống
* Cũng giống như bin, thư mục này còn chứa các chương trình thực thi chỉ dành cho admin để bảo trì hệ thống như reboot,fdisk...(***Fdisk là một tiện ích text-based được sử dụng để xem và quản lý các phân vùng ổ cứng trên Linux. Nó là một trong những công cụ mạnh mẽ nhất mà bạn có thể dùng để quản lý phân vùng ổ cứng.)***

![Untitled](https://user-images.githubusercontent.com/63154819/99865747-83dd8900-2bde-11eb-9d51-13f3e225e476.png)
#### 1.3 Boot - Các file khởi động
* Trong thư mục bao gồm tất cả các file cần thiết để khởi động hệ thống được lưu tại đây. Bao gồm các tập tin được cấu hình cho quá trình khởi động hệ thống.

#### 1.4 dev - Các file thiết bị
* Chứa các tập tin chứng nhận cho các thiết bị hệ thống như phân vùng ổ cứng, thiết bị ngoại vi.... hay bất kì thiết bị nào được kết nối với hệ thống đều được lưu ở đây.
* Chứa các tập tin thiết bị. Nó chứa các tập tin thiết bị đầu cuối như là USB hoặc bất kì thiết bị nào được gắn vào hệ thống
  * /dev/console : Bàn giao tiếp hệ thống, là màn hình kết nối vật lý với hệ thống.
  * /dev/hd* : Giao diện Driver cho các ổ cứng IDE. Thiết bị /dev/hda1 chỉ partition đầu tiên trên ổ cứng had. Thiết bị /dev/had chỉ toàn bộ ổ cứng hda.
  * /dev/sd* : Giao diện Driver cho các ổ đĩa SCSI. Những ổ đĩa và partition này có cùng quy ước với thiết bị IDE /dev/hd*
  * dev/pty* : Driver hỗ trợ terminal giả, dùng cho việc đăng nhập từ xa, chẳng hạn như những phiên bản đăng nhập qua Telnet.
  
  ![Capture](https://user-images.githubusercontent.com/63154819/99866163-88f00780-2be1-11eb-9ac8-8b974e8957b9.PNG)

#### 1.5 etc - Các file cấu hình
##### Chứa các file tập tin cấu hình cần thiết cho tất cả các chương trình hay phần mềm.
* Thư mục này chứa các file cấu hình toàn cục của hệ thống. Có thể có nhiều thư mục con trong thư mục này nhưng nhìn chung chúng chứa các file script để khởi động hay phục vụ cho mục đích cấu hình chương trình trước khi chạy.
* ví dụ /etc/resolv.conf ,/etc/logrotate.conf.
#### 1.6 home - Thư mục người dùng.
* Thư mục này chứa các thư mục con đại diện cho mỗi user khi đăng nhập. Nơi đây là thư viện làm việc thường xuyên của người dùng. Khi người quản trị tạo tài khoản cho bạn họ sẽ cấp cho bạn một thư mục cùng tên với tài khoản này nằm trong thư mục /home. Bạn có mọi quyền thao tác trên thư mục của mình và mà không ảnh hưởng đến người dùng khác.
#### 1.7 lib - Thư viện hệ thống.
* Mỗi khi cài đặt phần mềm trên linux, các thư viện cũng tự động được download và chúng hầu hết được bắt đầu với lib*.. Đây là thư viện cơ bản của linux cần để làm việc. Không giống như windows các thư viện có thể chia sẻ và dùng chung cho các chương trình khác nhau. Đó là một lợi ích trong hệ thống tệp tin của linux.
#### 1.8 mnt
* Chứa các thư mục dùng để system admin thực hiện quá trình mount. Như đã nói, hệ điều hành linux coi tất cả các file và lưu trữ trên một cây chung. Đây chính là nơi tạo ra các thư mục để gắn các phân vùng ổ đĩa cứng cũng như các thiết bị khác vào. Sau khi được mount vào đây các thiết bị hay ổ cứng được truy cập từ đây như là một thư mục. Trong một số hệ điều hành, các ổ đĩa chưa được gắn vào hệ thống bởi fstab sẽ được gắn ở đây.
#### 1.9 opt - Các ứng dụng phụ tùy chọn hoặc thêm
* Tên thư mục này nghĩa là Optional (tùy chọn), nó chứa các ứng dụng thêm vào từ các nhà cung cấp độc lập khác. Các ứng dụng này có thể được cài ở /opt hoặc một thư mục con của /opt.
* Nó chứa các ứng dụng được thêm vào từ các nhà cung cấp độc lập khác chưa có trong hệ thống ứng dụng Software Application. Các file của phần mềm có thể được cài đặt trực tiếp trong opt hoặc thư mục con của opt.
#### 1.10 proc - Thông tin các tiến trình
* Là một thư mục đặc biệt linh động dùng để lưu các thông tin về tình trạng của hệ thống, nhất là các tiến trình đang hoạt động dưới dạng một hệ thống file thư mục mô phỏng.
#### 1.11 root 
* Là thư mục dành riêng cho người quản trị hệ thống.
#### 1.12 run
* Là thư mục đồng hành cùng var/run. Nghĩa là trong var/run có gì thì run có thứ đó. Chúng được liên kết với nhau.
#### 1.13 srv
* Thư mục chứa các dữ liệu liên quan đến các dịch vụ chạy trên hệ thống như ssh, mysql, mongose....
* Chứa dữ liệu liên quan tới các dịch vụ trên máy chủ.
#### 1.14 var
* Lưu lại các tập tin với các số liệu biến đổi. Chẳng hạn như các tập tin về dữ liệu, các bản ghi.
usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone      Clone a repository into a new directory
   init       Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add        Add file contents to the index
   mv         Move or rename a file, a directory, or a symlink
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect     Use binary search to find the commit that introduced a bug
   grep       Print lines matching a pattern
   log        Show commit logs
   show       Show various types of objects
   status     Show the working tree status

grow, mark and tweak your common history
   branch     List, create, or delete branches
   checkout   Switch branches or restore working tree files
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   merge      Join two or more development histories together
   rebase     Reapply commits on top of another base tip
   tag        Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch      Download objects and refs from another repository
   pull       Fetch from and integrate with another repository or a local branch
   push       Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone      Clone a repository into a new directory
   init       Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add        Add file contents to the index
   mv         Move or rename a file, a directory, or a symlink
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect     Use binary search to find the commit that introduced a bug
   grep       Print lines matching a pattern
   log        Show commit logs
   show       Show various types of objects
   status     Show the working tree status

grow, mark and tweak your common history
   branch     List, create, or delete branches
   checkout   Switch branches or restore working tree files
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   merge      Join two or more development histories together
   rebase     Reapply commits on top of another base tip
   tag        Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch      Download objects and refs from another repository
   pull       Fetch from and integrate with another repository or a local branch
   push       Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
