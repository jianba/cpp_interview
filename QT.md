## 一、C/C++/数据结构20道题
1、sizeof/strlen区别？C语言中malloc和C++语言中new有何区别？C/C++程序编译的内存分配情况？

```
sizeof和strlen的区别：

sizeof是一个操作符，可以用来获取一个变量或类型的字节数，不受变量值的影响。例如，sizeof(int)返回4，sizeof(char)返回1。 strlen是一个函数，用于获取一个字符串的长度，即字符数组中的字符个数，不包括字符串结束符'\0'。例如，strlen("hello")返回5。

malloc和new的区别：

malloc和new都是用于在堆上分配内存的函数。它们的主要区别在于以下几点：

malloc返回一个void*指针，需要强制转换为目标类型指针，而new直接返回目标类型指针。

malloc只负责分配内存，不会自动调用构造函数，而new在分配内存后会自动调用构造函数。

malloc分配的内存可以使用free函数释放，而new分配的内存必须使用delete操作符释放。

C/C++程序编译的内存分配情况：

在C/C++程序编译时，内存分配主要分为以下几种情况：

栈内存分配：用于存储局部变量和函数调用的参数和返回值。栈内存分配由编译器自动完成，不需要手动分配和释放。

堆内存分配：用于存储动态分配的内存，需要使用malloc或new函数手动分配，并在不需要时使用free或delete操作符释放。

全局变量和静态变量分配：在程序运行前就进行内存分配，存储在静态存储区或全局存储区，程序结束后才会释放。
```

2、strcpy/sprintf/memcpy它们之间区别？

```
strcpy、sprintf和memcpy都是C语言中的字符串和内存操作函数，它们之间的主要区别如下：

strcpy用于将一个字符串复制到另一个字符串中，比如将src字符串复制到dest字符串中。函数原型为：char *strcpy(char *dest, const char *src)；

sprintf用于将格式化的数据转换成字符串并存储到另一个字符串中，比如将格式化的数字或文本保存到buf字符串中。函数原型为：int sprintf(char *buf, const char *format, ...)；

memcpy用于将一段内存的内容复制到另一个内存中，比如将src内存的内容复制到dest内存中。函数原型为：void *memcpy(void *dest, const void *src, size_t n)； 总的来说，这三个函数的作用不同，strcpy和memcpy主要用于字符串和内存的复制，而sprintf主要用于格式化数据的转换。使用时需要结合具体的需求选择合适的函数来操作。
```

3、面向对象的三大特征？C++语言的空类有哪些成员函数？

```
面向对象的三大特征是：

封装：将数据和操作数据的函数封装在一个类中，隐藏了具体实现细节，只暴露必要的接口给外部使用，保证了数据的安全性和可靠性。

继承：通过继承已有的类，可以扩展其功能，减少代码的冗余，提高代码的复用性和可维护性。

多态：通过函数重载、虚函数和模板等机制，实现不同对象对同一消息的不同响应，提高了程序的灵活性和可扩展性。

C++语言的空类是指没有任何成员变量和成员函数的类。空类默认会自动生成一些成员函数，包括默认构造函数、析构函数、拷贝构造函数和赋值运算符等。如果需要控制这些默认生成的成员函数的行为，可以通过定义相应的函数来实现。
```

4、多态实现的原理？链表和数组有何区别？队列和栈区别？

```
多态实现的原理：

多态是面向对象编程中的一种重要概念，实现多态的关键是虚函数和指针。在C++中，通过将基类中的某个函数声明为虚函数，可以使得派生类中的同名函数成为虚函数，从而实现多态。当通过基类指针或引用调用虚函数时，会根据指针或引用实际指向的对象类型来调用相应的函数，实现了动态绑定。这样就可以在不同的对象之间实现相同的操作，提高了代码的复用性和可维护性。

链表和数组的区别：

链表和数组都是常见的数据结构，它们的主要区别在于：

数组是一组具有相同数据类型的元素的集合，可以通过下标来访问每个元素，但是数组的长度是固定的，不能动态改变。

链表是由一组节点构成的数据结构，每个节点包含数据和指向下一个节点的指针，可以动态添加、删除、修改节点，但是访问链表中的元素需要遍历整个链表，效率较低。

队列和栈的区别：

队列和栈都是常见的数据结构，它们的主要区别在于：

队列是一种先进先出（FIFO）的数据结构，可以在队列的一端插入元素，在队列的另一端删除元素，典型的应用是操作系统的进程调度。

栈是一种后进先出（LIFO）的数据结构，可以在栈顶插入和删除元素，典型的应用是函数调用和表达式求值。
```



5、&&/&l有什么区别？Typedef/define/const/static有什么区别？

```
&&是逻辑与运算符，表示两个条件都为真时结果为真。

&是位运算符，表示对两个数的位进行与运算。

||是逻辑或运算符，表示两个条件中有一个为真时结果为真。

|是位运算符，表示对两个数的位进行或运算。

Typedef/define/const/static 有什么区别？

typedef：用来给数据类型取一个新的名字，方便在程序中使用。例如：typedef int INT; 表示将int类型取一个新的名字INT。

define：用来定义常量或宏，会在编译时被预处理器替换为定义的内容。例如：#define PI 3.14159 表示将PI定义为3.14159。

const：用来定义常量，在程序中不可修改。例如：const int MAX_NUM = 100; 表示将MAX_NUM定义为100，不可修改。

static：用来定义静态变量，静态变量只会被初始化一次，不会随函数的调用而重复初始化。静态变量的作用域只在定义它的函数内，但是它的值会被保留。静态函数只能在定义它的文件内使用。
```

6、如何避免“野指针”？

```
野指针是指指向无效内存地址的指针，它的出现往往会导致程序崩溃或者产生不可预期的结果。为了避免野指针的出现，可以采取以下措施：

将指针初始化为NULL或nullptr，即空指针，可以防止指针误用。

在指针被释放之后，将其赋值为NULL或nullptr，可以避免指针成为野指针。

使用智能指针，智能指针可以自动管理动态内存，避免内存泄漏和野指针问题。

避免指针操作过程中越界访问数组，可以使用STL容器代替数组，STL容器可以自动管理内存。

对于指向栈上的变量的指针，需要注意其生命周期，避免在变量被销毁后仍然使用指针。 总之，在程序中使用指针时，需要时刻保持警惕，避免出现野指针问题。
```

7、向链表的末尾添加一个元素？从链表尾部到头部打印结点信息？如何合并两个有序链表？

```
向链表的末尾添加一个元素的步骤如下：

新建一个节点，为其赋值；

遍历链表，找到最后一个节点；

将最后一个节点的next指针指向新节点；

新节点的next指针赋值为NULL，表示链表的末尾。

从链表尾部到头部打印节点信息的步骤如下：

遍历链表，将每个节点的值存放在栈中；

遍历栈，将栈中的值弹出并输出，即为链表的逆序输出。

合并两个有序链表的步骤如下：

新建一个空链表，作为合并后的链表；

遍历两个有序链表，比较当前两个链表的节点值，将较小的节点插入到新链表中；

如果其中一个链表已经遍历完，将另一个链表剩余的节点插入到新链表的末尾；

返回新链表。

示例代码如下：

// 向链表的末尾添加一个元素`
`void addNode(Node* head, int val) {`
    `Node* newNode = new Node(val);`
    `Node* cur = head;`
    `while (cur->next != NULL) {`
        `cur = cur->next;`
    `}`
    `cur->next = newNode;`
`}`
`// 从链表尾部到头部打印节点信息`
`void printListReverse(Node* head) {`
    `stack<Node*> s;
    Node* cur = head;`
    `while (cur != NULL) {`
        `s.push(cur);`
        `cur = cur->next;`
    `}`
    `while (!s.empty()) {`
        `Node* node = s.top();`
        `s.pop();`
        `cout << node->val << " ";`
    `}`
`}`
`// 合并两个有序链表`
`Node* mergeList(Node* head1, Node* head2) {`
    `Node* dummy = new Node(-1);`
    `Node* cur = dummy;`
    `while (head1 != NULL && head2 != NULL) {`
        `if (head1->val < head2->val) {`
            `cur->next = head1;`
            `head1 = head1->next;`
        `} else {`
            `cur->next = head2;`
            `head2 = head2->next;`
        `}`
        `cur = cur->next;`
    `}`
    `if (head1 != NULL) {`
        `cur->next = head1;`
    `}`
    `if (head2 != NULL) {`
        `cur->next = head2;`
    `}`
    `return dummy->next;`
`}`
```

8、如何反转链表？判断链表是否是回文链表？如何判断链表相交？

9、假设现有n个有序数组，如何合并成一个有序数组？

10、栈和队列、字符串、树、递归、AVL树、红黑树、哈弗曼编码、B+树、map/unordered_map、动态规划。

```
栈和队列、字符串、树、递归、AVL树、红黑树、哈夫曼编码、B+树、map/unordered map、动态规划是常见的数据结构或算法。

栈和队列：栈和队列是线性数据结构，栈是后进先出，队列是先进先出。

字符串：字符串是由字符组成的序列，常用于文本处理、模式匹配等。

树：树是非线性数据结构，由节点和边组成，每个节点可以有多个子节点。

递归：递归是一种算法或编程技巧，通过函数自身调用实现问题的分解和求解。

AVL树：AVL树是自平衡二叉搜索树，保证任意节点的左右子树高度差不超过1。

红黑树：红黑树也是自平衡二叉搜索树，通过变色和旋转操作来保持平衡。

哈夫曼编码：哈夫曼编码是一种将字符编码为二进制的算法，通过构建哈夫曼树来实现。

B+树：B+树是一种多路搜索树，常用于数据库索引等场景。

map/unordered map：map和unordered map是键值对的容器，支持O(1)的查找和O(logn)的插入、删除等操作。

动态规划：动态规划是一种求解最优化问题的算法，通过将大问题分解为小问题求解
```

11、什么时候产生默认拷贝构造函数？什么是深拷贝？什么是浅拷贝？

```
默认拷贝构造函数会在以下情况下自动生成：

如果没有定义自己的拷贝构造函数，且类的成员变量都是可拷贝的，则编译器会自动生成默认的拷贝构造函数；

如果定义了拷贝构造函数，但没有实现任何操作，则编译器也会自动生成默认的拷贝构造函数。

深拷贝和浅拷贝是指在拷贝对象时，是否会将对象的动态内存也复制一份。 深拷贝是指在拷贝对象时，会将对象的动态内存也复制一份，每个对象都有自己的一份动态内存，互不干扰。

浅拷贝是指在拷贝对象时，只是将对象的指针或引用复制一份，两个指针指向同一个动态内存，修改其中一个对象的动态内存会影响到另一个对象。

在使用动态内存分配时，如果不进行深拷贝，可能会导致多个对象共享同一块动态内存，当一个对象释放动态内存时，其他对象也会受到影响，可能会导致程序崩溃或数据错误。因此，在使用动态内存分配时，通常需要进行深拷贝。
```

12、虚析函数的作用？Vector底层实现原理？

```
虚析函数的作用是防止在子类析构时只调用了父类的析构函数，而没有调用子类的析构函数，导致内存泄漏和资源释放不完全的问题。通过将基类析构函数声明为虚析函数，可以确保在子类析构时会先调用子类的析构函数，再调用父类的析构函数，从而避免这种问题。

Vector是一种动态数组，底层实现原理是使用连续的内存块来存储元素，并且在需要扩容时重新分配更大的内存块，并将原有元素拷贝到新的内存块中。具体来说，Vector在创建时会分配一块初始大小的内存，当元素个数超过该内存大小时，会重新分配一块更大的内存，并将原有元素拷贝到新内存中，同时释放原有内存。此过程涉及到内存分配、拷贝和释放，因此Vector的效率受到内存管理的影响。为了避免频繁的内存分配和拷贝，Vector通常会预先分配一定的内存空间，以减少扩容的次数。
```

13、deque底层实现原理？

```
deque（双端队列）底层实现原理是使用一段连续的存储空间，被分配为多个内存块，每个内存块独立分配，内部使用指针互相连接。deque中包含一个中控器，中控器中存放着指向第一块内存块和最后一块内存块的迭代器，以及指向每个内存块的迭代器，中控器的作用是管理内存块的分配和释放，并提供访问内存块的接口。

deque的元素在内存中并不是连续存储的，而是分散存储在不同的内存块中，但是中控器提供的接口使得deque的使用者可以像访问连续存储空间一样访问deque的元素，即可以使用迭代器、下标操作符等对deque进行遍历和访问。

对于deque的插入和删除操作，由于元素在内存中是分散存储的，因此需要在中控器中进行内存块的分配和释放，并更新迭代器指向。由于deque的实现比较复杂，因此相比于vector等容器，deque的效率相对较低，但是deque在某些场景下具有优势，比如插入和删除操作比较频繁、需要在deque的两端进行操作等。
```

14、左值引用与右值引用区别？右值引用意义？

```
左值引用和右值引用是C++11中引入的新特性，它们的主要区别在于引用的类型和绑定的对象。

左值引用是指对一个左值（可以取地址、有名字的变量或者对象、表达式或函数返回值）进行的引用，它的类型为T&，可以对其进行修改或者取地址等操作。

右值引用是指对一个右值（不能取地址、没有名字的临时对象或者表达式）进行的引用，它的类型为T&&，通常用于移动语义和完美转发等场景。右值引用的一个重要作用是支持移动语义，即通过将右值引用参数移动到目标对象中，避免了昂贵的内存拷贝操作，提高了程序的效率。

右值引用的意义在于提供了一种新的引用类型，使得我们可以更加高效地处理临时对象和表达式，同时也支持了新的语言特性，比如移动语义和完美转发等。右值引用还可以用于实现移动构造函数和移动赋值运算符等操作，从而提高程序的效率和性能。
```

15、索引为什么要使用B+树而不是二叉树或者B树？

```
索引是数据库中常用的数据结构，用于加速数据的查询和检索。B+树相对于二叉树和B树的优势在于其更适合于磁盘存储的特点，主要表现在以下几个方面：

减少磁盘I/O开销：B+树的每个节点可以存储更多的关键字，因此可以减少磁盘I/O操作的次数。相比较而言，B树每个节点的关键字数目较少，因此需要更多的I/O操作，而二叉树的高度也可能很大，导致I/O次数增多。

便于范围查询：B+树的叶子节点形成了一个有序链表，可以方便地进行范围查询。相比较而言，B树和二叉树需要在非叶子节点进行回溯才能找到所有满足条件的记录，这会增加额外的开销。

便于扫描操作：B+树的叶子节点形成了一个有序链表，可以方便地进行顺序扫描，以及分页查询等操作。相比较而言，B树和二叉树需要在非叶子节点进行回溯才能找到下一个节点，这会增加额外的开销。 因此，在需要进行大量磁盘I/O操作的场景下，B+树是更加合适的选择。而在内存中的数据结构，比如红黑树和哈希表等，由于磁盘I/O操作的次数较少，因此使用B+树并不会带来很大的优势。
```

16、SQL流入原理？如何避免SQL注入？

```
SQL注入是一种常见的Web攻击方式，攻击者通过在输入框中注入特定的SQL语句，从而获取敏感数据或者控制数据库。为了避免SQL注入，需要采取一些措施，包括以下几个方面：

使用参数化查询：参数化查询可以避免将用户输入的数据直接拼接到SQL语句中，从而避免SQL注入。参数化查询可以将用户输入的数据作为参数传递给SQL语句，而不是直接拼接到SQL语句中。这样，即使用户输入了恶意的SQL语句，也不会对数据库造成影响。

对用户输入进行过滤和验证：对用户输入进行验证和过滤可以避免非法字符和SQL关键字的注入。例如，可以使用正则表达式或者特定的函数对用户输入进行过滤，从而确保输入的数据符合预期的格式。

最小化数据库权限：为了最小化数据库被攻击的风险，应该为数据库分配最小的权限。例如，只授权给应用程序需要的最小权限，避免将管理员权限授予普通用户。

使用防火墙和安全软件：使用防火墙和安全软件可以检测和拦截恶意的SQL语句，从而保护数据库的安全。 SQL流入是指将SQL注入攻击的尝试记录下来，分析攻击的方式和来源，从而采取相应的措施。SQL流入可以通过日志分析软件或者数据库自身的审计功能来实现。通过SQL流入，可以及时发现SQL注入攻击，采取相应的措施保护数据库的安全
```

17、MySQL死锁问题产生原因及如何解决？

```
MySQL死锁是指两个或多个事务相互等待对方释放锁，从而导致事务无法继续执行的情况。产生死锁的原因主要有以下几个方面：

并发访问：多个事务同时访问同一个资源（例如表、行、页等），并且访问方式不同（例如读、写等），从而导致锁的冲突。

锁的顺序：多个事务请求锁的顺序不同，从而导致死锁的产生。

锁的粒度：锁的粒度太细或者太大，都可能导致死锁的产生。 为了解决MySQL死锁问题，可以采取以下几个措施：

优化SQL语句：通过优化SQL语句，减少事务的数量和时间，从而减少死锁的发生概率。

调整锁的粒度：通过调整锁的粒度，使得锁的数量和范围都适当，从而减少死锁的发生概率。

调整事务隔离级别：通过调整事务隔离级别，使得事务的访问方式和范围适当，并且避免两个事务同时对同一个资源进行修改。

监控死锁：通过监控死锁，及时发现死锁的产生，并采取相应的措施解决死锁问题。

加锁顺序：使用相同的加锁顺序，从而避免死锁问题的发生。

限制事务等待时间：通过限制事务等待时间，使得事务在等待一定时间后自动回滚，从而避免死锁的长时间占用资源。 通过以上措施，可以有效地解决MySQL死锁问题，提高数据库的性能和稳定性。
```

18、TCP三次握手的过程/为什么不可以两次握手？

```
TCP三次握手是TCP协议建立可靠连接的过程，其过程如下：

客户端发送SYN包给服务器，表示请求建立连接。

服务器收到客户端的SYN包后，发送ACK包给客户端，表示确认请求，并发送自己的SYN包给客户端。

客户端收到服务器的ACK包和SYN包后，发送ACK包给服务器，表示确认连接建立。

因为TCP协议是面向连接的协议，需要在建立连接之后才能进行数据传输。三次握手的过程可以确保建立连接的可靠性，防止因为网络延迟或者丢包导致连接建立失败。如果只进行两次握手，就不能确定对方已经接收到自己的SYN包，也就不能确定是否建立连接。例如，如果客户端发送SYN包后，服务器没有收到，那么客户端会一直等待ACK包，而服务器会认为连接已经建立。这样就会导致数据的不可靠性和安全性问题。因此，TCP协议需要进行三次握手，以确保连接的可靠性。
```

19、TCP四次挥手的过程？TCP是如何保证可靠性？

```
TCP四次挥手是TCP协议结束连接的过程，其过程如下：

客户端发送FIN包给服务器，表示请求关闭连接。

服务器收到客户端的FIN包后，发送ACK包给客户端，表示确认关闭请求，并且告诉客户端可以关闭连接了。

服务器发送自己的FIN包给客户端，表示请求关闭连接。

客户端收到服务器的FIN包后，发送ACK包给服务器，表示确认关闭请求，并且告诉服务器可以关闭连接了。 TCP协议通过以下几个机制来保证可靠性：

序列号和确认应答：TCP协议在传输数据时，会为每一个数据包设置一个序列号，接收方收到数据包后，需要发送一个确认应答包，告诉发送方收到了哪些数据包。如果发送方没有收到确认应答包，就会重新发送数据包，直到接收方确认收到为止。

超时重传：如果发送方发送了一个数据包，但是没有收到确认应答包，就会重新发送数据包，直到收到确认应答或者达到重传次数上限为止。

滑动窗口：TCP协议中，发送方和接收方都有一个滑动窗口，用来控制数据流的传输。发送方根据接收方的确认应答，动态调整窗口大小，控制数据的发送速度。接收方根据需要，动态调整窗口大小，控制数据的接收速度。

流量控制：TCP协议中，通过滑动窗口来控制数据流的传输，可以防止发送方发送过多的数据，导致接收方无法处理。

拥塞控制：TCP协议中，通过动态调整窗口大小和发送速度，来控制网络拥塞的发生，保证网络的稳定性和可靠性。 通过以上机制，TCP协议可以保证数据的可靠传输，同时也可以保证网络的稳定性和可靠性。
```

20、什么是连接半打开，头关闭状态？

```
连接半打开状态（TCP SYN_SENT状态）是指TCP连接建立过程中，客户端发送SYN包给服务器，但是服务器还没有发送ACK包进行确认的状态。在这个状态下，客户端等待服务器的确认，如果服务器没有响应，则客户端会发送多个SYN包，直到建立连接或者达到重试次数上限为止。

头关闭状态（TCP FIN_WAIT_1和FIN_WAIT_2状态）是指TCP连接关闭过程中，发送方（可以是客户端也可以是服务器）发送FIN包给接收方，请求关闭连接之后，等待接收方的ACK包的状态。在FIN_WAIT_1状态下，发送方等待接收方的ACK包，如果接收方没有回复，则发送方会重新发送FIN包；在FIN_WAIT_2状态下，发送方等待接收方的FIN包，如果接收方没有发送FIN包，则发送方会一直等待直到超时。

在连接半打开状态和头关闭状态下，TCP连接可能会出现异常情况，例如网络延迟、丢包等，导致连接无法正常建立或关闭。因此，在使用TCP协议时，需要注意处理连接半打开状态和头关闭状态，以确保连接的可靠性和稳定性。
```



##  二、Qt编程技术常见30道题
1、Qt信号槽机制的优点及缺点？

```
Qt信号槽机制是一种事件驱动的编程模型，它的优点和缺点如下：

优点：

松耦合：信号槽机制可以实现组件之间的松耦合，组件之间不需要直接相互调用，只需要通过信号和槽进行通信即可，这样可以降低组件之间的耦合度，提高代码的复用性和可维护性。

灵活性：信号槽机制可以实现非常灵活的事件处理，可以动态的连接和断开信号和槽，可以在运行时动态修改信号和槽的参数等。

易于扩展：信号槽机制可以非常容易地扩展新的事件和处理逻辑，只需要定义新的信号和槽即可，无需修改原有代码。

跨线程：信号槽机制可以支持跨线程的事件处理，可以将信号和槽连接在不同的线程中，这样可以实现线程之间的通信。

缺点：

性能：信号槽机制的性能相对于直接调用函数来说会有一定的开销，因为它需要进行信号的发射和槽的执行，而且还需要维护信号槽的连接关系。

调试：由于信号槽机制是基于事件驱动的编程模型，因此调试起来可能会比较困难，特别是在信号和槽之间存在多层嵌套的情况下。

安全性：由于信号槽机制可以动态连接和断开信号和槽，因此在使用时需要注意安全性问题，避免出现槽函数被误调用的情况。 总的来说，Qt信号槽机制是一种非常灵活和方便的事件驱动编程模型，它的优点在于松耦合、灵活性、易于扩展和跨线程等方面，但是在性能、调试和安全性等方面需要注意一些问题。
```

2、Qt如何实现自定义按钮，使其在光标进入、按下、离开三种状态下显示不同的图片？

3、Qt信号和槽本质？

```
Qt中的信号和槽是一种事件驱动的机制，用于在对象之间传递消息和实现对象间的通信。信号和槽的本质可以解释为以下两个方面：

信号和槽本质是函数：

在Qt中，信号和槽本质上是函数，信号是一种特殊的函数，它不包含函数体，只有函数声明和参数列表，用于向外部发出某种事件的通知。槽也是一种函数，它是一个普通的成员函数，用于处理信号发出的事件。在信号和槽连接时，实际上是将信号函数和槽函数通过一个中介对象（连接器）连接起来，使得信号函数能够调用槽函数，从而实现对象间的通信。

信号和槽本质是元对象系统的一部分：

在Qt中，信号和槽是元对象系统的一部分，元对象系统是一个用于支持Qt元编程的框架，它允许在运行时动态地查询和操作对象的元数据，包括类名、属性、方法等。信号和槽的实现依赖元对象系统的元数据，每个QObject对象在创建时都会生成一个元对象，其中包含了该对象的所有信息，包括信号和槽的声明和实现。当信号和槽连接时，会根据元数据进行检查和匹配，保证信号和槽的正确连接和调用。

综上所述，信号和槽本质上是函数，它们通过元对象系统实现对象间的通信，使得对象之间能够相互响应和交互，是Qt中非常重要的一种机制。
```

4、Qt当中的数据流(QDataStream)和文件流(QTextStream)）有何区别？

```
Qt中的数据流(QDataStream)和文件流(QTextStream)都是用于读写数据的流类，但它们有以下区别：

数据类型：数据流(QDataStream)支持Qt中的所有基本数据类型和自定义类型，如QString、QByteArray等，而文件流(QTextStream)只能读写文本数据，不支持二进制数据。

数据格式：数据流(QDataStream)是二进制格式，可以直接读写二进制数据，而文件流(QTextStream)是文本格式，只能读写文本数据，对于二进制数据需要进行编码和解码。

数据编码：文件流(QTextStream)默认使用Unicode编码，可以通过设置不同的编码格式来读写不同的文本数据，而数据流(QDataStream)不需要进行编码，它直接以二进制形式读写数据。

应用场景：数据流(QDataStream)适用于读写二进制数据，例如读写文件、网络传输等场景，而文件流(QTextStream)适用于读写文本数据，例如读写配置文件、日志文件等场景。

综上所述，数据流(QDataStream)和文件流(QTextStream)虽然都是Qt中的流类，但它们的数据类型、格式、编码和应用场景等方面有所不同，需要根据具体的需求选择合适的流类进行读写操作。
```

5、Qt网络通信中，TCP./UDP整体流程（服务器，客户端）

```
在Qt中，TCP/UDP网络通信的整体流程主要包括以下步骤：

服务器端的创建和监听

服务器端首先需要创建一个QTcpServer或QUdpSocket对象，用于监听客户端的连接或接收数据。创建时需要指定端口号和IP地址（如果有多个网卡，则需要指定监听的网卡地址）。然后调用listen()函数开始监听客户端的连接或数据包的到来。

客户端的连接或数据发送

客户端需要创建一个QTcpSocket或QUdpSocket对象，用于连接服务器或发送数据包。对于TCP通信，客户端需要调用connectToHost()函数连接服务器；对于UDP通信，客户端可以直接使用writeDatagram()函数发送数据包。

服务器端的响应和数据处理

当客户端连接到服务器或发送数据包时，服务器端会触发相应的信号（如newConnection()、readyRead()等），在相应的槽函数中进行响应和数据处理。对于TCP通信，服务器端需要在newConnection()槽函数中调用nextPendingConnection()函数获取客户端的QTcpSocket对象，然后在客户端的QTcpSocket对象上调用read()函数读取数据；对于UDP通信，服务器端可以直接在readyRead()槽函数中调用readDatagram()函数读取数据包。

客户端的数据接收和响应

当客户端连接到服务器或发送数据包时，客户端会触发相应的信号（如connected()、readyRead()等），在相应的槽函数中进行数据接收和响应。对于TCP通信，客户端需要在connected()槽函数中调用write()函数发送数据，然后在readyRead()槽函数中调用read()函数读取服务器端的响应数据；对于UDP通信，客户端可以直接在readyRead()槽函数中调用readDatagram()函数读取服务器端的响应数据包。

断开连接和清理资源

当通信完成或出现错误时，需要断开连接并清理资源。对于TCP通信，可以在客户端或服务器端的QTcpSocket对象上调用disconnectFromHost()函数或close()函数断开连接，并在socketDisconnected()槽函数中清理资源；对于UDP通信，不需要显式地断开连接，系统会自动管理资源。

综上所述，TCP/UDP网络通信的整体流程包括服务器端的创建和监听、客户端的连接或数据发送、服务器端的响应和数据处理、客户端的数据接收和响应，以及断开连接和清理资源。根据具体的需求，可以选择使用QTcpServer、QTcpSocket、QUdpSocket等类进行开发。
```

6、Qt编程当中，多线程的两种使用方法？

```
在Qt编程中，多线程的两种使用方法分别是：

继承QThread类 继承QThread类是一种常见的多线程编程方法。该方法需要定义一个新类，继承自QThread类，并重写run()函数，run()函数中包含了需要在新线程中执行的代码。在主线程中创建该类的实例对象，调用start()函数启动新线程。 示例代码：
class MyThread : public QThread
{
    Q_OBJECT
public:
    void run() override
    {
        // 在新线程中执行的代码
    }
};
MyThread thread;
thread.start();
2.继承QObject类，使用QThread对象 继承QObject类，使用QThread对象是另一种常见的多线程编程方法。该方法需要定义一个新类，继承自QObject类，并在该类中定义需要在新线程中执行的槽函数。在主线程中创建QThread对象，将新类的实例对象移动到该QThread对象所在的线程中，然后启动该QThread对象。 示例代码：

class MyObject : public QObject
{
    Q_OBJECT
public slots:
    void doWork()
    {
        // 在新线程中执行的代码
    }
};
QThread thread;
MyObject *obj = new MyObject();
obj->moveToThread(&thread);
QObject::connect(&thread, &QThread::started, obj, &MyObject::doWork);
thread.start();
以上两种方法都可以实现多线程编程，选择哪种方法取决于具体的需求和编程风格。需要注意的是，在多线程编程中，需要注意线程间的同步和互斥问题，避免出现竞态条件和死锁等问题。可以使用Qt提供的线程同步机制（如QMutex、QWaitCondition等）或标准的C++11线程库（如std::mutex、std::condition_variable等）进行处理。
```

7、创建signal类？QVariant应用？

```
在Qt中，创建signal类可以通过继承QObject类并使用signals关键字来声明信号。一个signal类通常包含一个或多个信号，每个信号都由一个信号名称和一个信号参数列表组成，其中信号参数列表可以为空。示例代码如下：

class MySignalClass : public QObject
{
    Q_OBJECT
public:
    MySignalClass(QObject *parent = nullptr) : QObject(parent) {}
signals:
    void mySignal(int value);
    void anotherSignal(QString text, int count);
};
在上面的代码中，MySignalClass类继承自QObject类，并使用signals关键字声明了两个信号，分别是mySignal和anotherSignal，其中mySignal信号有一个int类型的参数，anotherSignal信号有一个QString类型和一个int类型的参数。 QVariant是Qt中一个用于封装任意类型数据的类，它可以用于在不同类型之间进行数据转换。可以使用QVariant::fromXXX()函数将不同类型的数据转换为QVariant类型，如QVariant::fromInt()、QVariant::fromString()等；可以使用QVariant::toXXX()函数将QVariant类型的数据转换为其他类型，如QVariant::toInt()、QVariant::toString()等。示例代码如下：

QVariant var = QVariant::fromInt(123); // 将int类型的数据转换为QVariant类型
int value = var.toInt(); // 将QVariant类型的数据转换为int类型
在上面的代码中，QVariant::fromInt()函数将int类型的数据转换为QVariant类型，QVariant::toInt()函数将QVariant类型的数据转换为int类型。需要注意的是，QVariant类型的数据转换可能会存在精度损失和类型错误等问题，需要根据实际情况进行处理。
```

8、(Qt中的指针：QPointerQScopedPointerQSharedPointer.QWeakPointer、std:weak_ptr、QSharedDataPointer

```
在Qt中，指针是一个很重要的概念，Qt提供了多种指针类来帮助我们管理内存和避免内存泄漏。下面是对常见的指针类进行简要介绍：

QPointer QPointer是Qt中的智能指针，它可以自动管理指针的生命周期，并且可以检测被管理的对象是否已经被销毁。如果被管理的对象已经被销毁，QPointer会自动将指针置为nullptr。QPointer通常用于管理QWidget对象等需要在程序运行期间动态创建和销毁的对象。

QScopedPointer QScopedPointer是Qt中的局部智能指针，它可以自动管理指针的生命周期，并且可以在指针超出作用域时自动释放指针指向的内存。QScopedPointer通常用于管理局部变量和堆内存对象等需要在作用域结束时自动释放的对象。

QSharedPointer QSharedPointer是Qt中的共享智能指针，它可以在多个指针之间共享同一个对象，并且可以自动管理指针的生命周期。当最后一个指向对象的QSharedPointer被销毁时，QSharedPointer会自动释放对象的内存。QSharedPointer通常用于管理需要在多个地方使用同一个对象的情况。

QWeakPointer QWeakPointer是Qt中的弱智能指针，它类似于QSharedPointer，但是不会增加对象的引用计数。QWeakPointer通常用于在多个指针之间共享同一个对象时，避免产生循环引用问题。

std::weak_ptr std::weak_ptr是C++11标准库中的弱智能指针，它类似于QWeakPointer，但是不是Qt所提供的。std::weak_ptr可以用于在多个指针之间共享同一个对象时，避免产生循环引用问题。

QSharedDataPointer QSharedDataPointer是Qt中的共享数据指针，它可以在多个对象之间共享同一个数据，而不需要共享整个对象。QSharedDataPointer通常用于实现copy-on-write（COW）技术，避免不必要的复制操作。 需要注意的是，不同的指针类适用于不同的场景和需求，需要根据实际情况进行选择和使用。
```

9、Qt当中的show和exec区别？

```
在Qt中，show和exec都是用来显示对话框的方法，它们的主要区别在于它们的运行机制和返回值。

show方法是在当前线程中显示对话框并立即返回，该方法不会阻塞当前线程，因此当对话框显示后，程序会继续执行后续代码。如果在对话框显示期间需要执行一些其他操作，可以在对话框关闭事件中处理，或者使用Qt的事件循环机制（如QEventLoop）来阻塞程序执行。

exec方法是在当前线程中显示对话框，并且阻塞当前线程，直到用户关闭对话框为止。在执行exec方法后，程序会进入一个事件循环（QEventLoop），直到对话框关闭事件被触发。因此，如果需要在对话框关闭之前执行一些其他操作，需要在对话框关闭事件之前处理。

需要注意的是，show方法和exec方法都可以用来显示对话框，但是它们的使用场景不同。show方法通常用于显示模态对话框和非模态对话框，而exec方法通常用于显示模态对话框。如果需要在对话框显示期间执行一些其他操作，建议使用show方法，如果需要等待用户关闭对话框后再执行其他操作，建议使用exec方法。
```

10、QString与基本数据类型如何转换？

```
在Qt中，QString与基本数据类型之间可以进行方便的相互转换。下面是常见的转换方法：

将QString转换为基本数据类型 通过QString的各种转换函数，可以将QString转换为int、float、double等基本数据类型。例如：

QString str = "123";
int num = str.toInt(); // 将QString转换为int类型
float f = str.toFloat(); // 将QString转换为float类型
double d = str.toDouble(); // 将QString转换为double类型
2.将基本数据类型转换为QString 通过QString的静态函数，可以将int、float、double等基本数据类型转换为QString。例如：

1. int num = 123;
   QString str = QString::number(num); // 将int类型转换为QString
   float f = 3.14;
   QString str2 = QString::number(f); // 将float类型转换为QString
需要注意的是，QString和基本数据类型之间的转换可能会存在精度和数据溢出等问题，需要根据实际情况进行选择和处理。
```

11.QMap类/QHash类/QVectoro类作用和区别？

```
1、在Qt中，QMap类、QHash类和QVector类都是用来管理数据的容器类，它们的作用和区别如下：

QMap类 QMap类是一种有序的映射容器，它可以将一个键值对映射到另一个键值对，且键值对是按照键的顺序进行排序的。QMap类通常用于对一组数据进行映射操作，常见的操作包括查找、插入、删除等。例如：
QMap<QString, int> map;
map.insert("Tom", 18);
map.insert("Jack", 20);
map.insert("Lucy", 17);
int age = map.value("Tom"); // 获取键为"Tom"的值
map.remove("Lucy"); // 删除键为"Lucy"的键值对
2.QHash类 QHash类是一种无序的哈希容器，它可以将一个键值对映射到另一个键值对，且键值对是按照哈希值进行存储的。QHash类通常用于对一组数据进行哈希操作，常见的操作包括查找、插入、删除等。例如：

QHash<QString, int> hash;
hash.insert("Tom", 18);
hash.insert("Jack", 20);
hash.insert("Lucy", 17);
int age = hash.value("Tom"); // 获取键为"Tom"的值
hash.remove("Lucy"); // 删除键为"Lucy"的键值对
3.QVector类 QVector类是一种动态数组容器，它可以存储任意类型的数据，并且支持动态增加和删除操作。QVector类通常用于存储一组数据，并且需要对数据进行动态操作，如排序、查找等。例如：

QVector<int> vec;
vec.append(1);
vec.append(2);
vec.append(3);
int num = vec.at(1); // 获取第2个元素
vec.removeLast(); // 删除最后一个元素
需要注意的是，QMap类、QHash类和QVector类应根据实际情况进行选择和使用。如果需要对数据进行排序和查找操作，建议使用QMap类；如果需要对数据进行哈希操作，建议使用QHash类；如果需要对数据进行动态操作，建议使用QVector类。
```

12、QList类/QLinkedList类作用？
13、请说出Qt常用8类56个控件？
14、QLayoutQStackedWidget类/QSplitter类/QDockWidget类?
15、Qt当中文件对话框、字体对话体、输入对话框、消息对话框
16、Qt绘制原理双缓冲机制？

```
Qt绘制原理中的双缓冲机制是指在绘制过程中使用两个缓冲区，一个用于绘制，一个用于显示，从而避免了绘制过程中的闪烁等问题。具体来说，双缓冲机制的实现过程如下：

创建两个缓冲区，一个用于绘制，一个用于显示；
在绘制过程中，将所有的绘制操作都先绘制到绘制缓冲区中；
绘制完成后，将绘制缓冲区中的内容复制到显示缓冲区中；
显示缓冲区中的内容会被显示在屏幕上。 这样，由于绘制操作是在绘制缓冲区中进行的，因此不会直接影响到显示缓冲区中的内容，从而避免了闪烁等问题。 在Qt中，双缓冲机制是由QPainter类和QWidget类共同实现的。QPainter类用于在绘制缓冲区中进行绘制操作，而QWidget类则在显示缓冲区中进行显示操作。具体来说，当QWidget类的paintEvent()函数被触发时，会创建一个QPainter对象，然后在其中调用绘制函数，将所有的绘制操作都绘制到绘制缓冲区中。绘制完成后，QPainter对象会自动将绘制缓冲区中的内容复制到显示缓冲区中，然后显示缓冲区中的内容会被显示在屏幕上。 需要注意的是，双缓冲机制虽然可以避免闪烁等问题，但是也会增加内存的消耗。因此，在实际应用中需要根据具体情况进行选择和使用。
```

17、GraphicsView图形视图框架结构？

```
Graphics View是Qt中用于显示和处理大量图形元素的框架，其主要包括以下几个重要的类和组件：

QGraphicsItem和QGraphicsScene：QGraphicsItem类是Graphics View框架中所有图形项的基类，它定义了所有图形项的共同属性和行为。QGraphicsScene类是Graphics View框架中的场景类，它管理着所有的图形项，并且提供了对它们进行操作的接口。
QGraphicsView：QGraphicsView类是Graphics View框架中的视图类，它用于在屏幕上显示QGraphicsScene中的内容，并且提供了对场景进行缩放、平移、旋转等操作的接口。
QGraphicsWidget：QGraphicsWidget类是Graphics View框架中的窗口类，它可以作为一个图形项添加到QGraphicsScene中，并且支持鼠标事件、键盘事件等交互操作。
QGraphicsProxyWidget：QGraphicsProxyWidget类是Graphics View框架中的窗口代理类，它可以将一个QWidget对象转换为一个图形项，然后添加到QGraphicsScene中。
QGraphicsItemGroup：QGraphicsItemGroup类是Graphics View框架中的图形项组类，它可以将多个图形项组合成一个整体，从而方便对它们进行操作。
QGraphicsEffect：QGraphicsEffect类是Graphics View框架中的特效类，它可以对QGraphicsItem进行图形效果的处理，例如模糊、阴影、发光等。
QGraphicsPixmapItem和QGraphicsTextItem：QGraphicsPixmapItem类是Graphics View框架中的图片项类，它可以将一个QPixmap对象显示在场景中。QGraphicsTextItem类是Graphics View框架中的文本项类，它可以将一个字符串显示在场景中。 以上是Graphics View框架的主要组件和类，它们共同构成了Graphics View框架的结构。通过这些组件和类的使用，我们可以方便地实现各种复杂的图形界面和图形效果。
```

18、Qt当中如何读写文件？

```
在Qt中，可以使用QFile类和QTextStream类来读写文件。

读文件：
QFile file("test.txt");
if (!file.open(QIODevice::ReadOnly | QIODevice::Text))
    return;
QTextStream in(&file);
while (!in.atEnd()) {
    QString line = in.readLine();
    // 处理每一行数据
}
file.close();
上述代码中，首先使用QFile类打开要读取的文件，然后使用QTextStream类对文件进行读取。通过while循环，每次读取一行数据，然后进行处理。最后关闭文件。

写文件：
QFile file("test.txt");
if (!file.open(QIODevice::WriteOnly | QIODevice::Text))
    return;
QTextStream out(&file);
out << "Hello world" << endl;
out << "Qt is awesome" << endl;
file.close();
上述代码中，首先使用QFile类打开要写入的文件，然后使用QTextStream类对文件进行写入。通过向QTextStream对象中写入数据，可以将数据写入文件中。最后关闭文件。 需要注意的是，在进行文件读写操作时，需要确保文件路径正确，并且文件权限足够。同时，需要根据具体情况使用不同的打开模式，例如只读模式、只写模式、追加模式等。
```

19、Qt中事件过滤处理方法？

```
Qt中的事件过滤器可以用于对某个对象的事件进行拦截和处理。事件过滤器是一个QObject对象，它可以安装到任何QObject派生类中，并且可以监听该对象的所有事件。当事件发生时，事件过滤器可以拦截并处理该事件，也可以将该事件转发给原始的事件接收者对象进行处理。 事件过滤器的处理方法如下：

创建一个QObject派生类，实现其eventFilter()函数，该函数会在事件发生时被调用。
class MyEventFilter : public QObject
{
    Q_OBJECT
public:
    explicit MyEventFilter(QObject *parent = nullptr);
protected:
    bool eventFilter(QObject *watched, QEvent *event) override;
};
2.在需要监听的对象中，调用installEventFilter()函数安装事件过滤器。

MyEventFilter *eventFilter = new MyEventFilter;
QLabel *label = new QLabel("Hello, World!");
label->installEventFilter(eventFilter);
3.在eventFilter()函数中处理事件，可以通过判断事件类型和事件源来对事件进行不同的处理。

bool MyEventFilter::eventFilter(QObject *watched, QEvent *event)
{
    if (watched == label && event->type() == QEvent::MouseButtonPress) {
        QMouseEvent *mouseEvent = static_cast<QMouseEvent *>(event);
        // 处理鼠标事件
        return true;
    }
    return false;
}
需要注意的是，在eventFilter()函数中返回true表示该事件已经被处理，不再继续传递给事件接收者对象进行处理；返回false表示该事件仍然需要传递给事件接收者对象进行处理。
```

20、Qt操作INI文件、JSON文件、XML文件？

```
Qt提供了三种常用的文件格式处理方式，分别是INI文件、JSON文件和XML文件。下面分别介绍如何在Qt中操作这三种文件格式。

操作INI文件 INI文件是一种常用的配置文件格式，在Qt中可以通过QSettings类来读写INI文件。以下是一个例子：
QSettings settings("myApp.ini", QSettings::IniFormat);
// 写入配置项
settings.setValue("General/Name", "Tom");
settings.setValue("General/Age", 20);
// 读取配置项
QString name = settings.value("General/Name").toString();
int age = settings.value("General/Age").toInt();
2.操作JSON文件 JSON是一种轻量级的数据交换格式，在Qt中可以通过QJsonDocument类和QJsonObject类来读写JSON文件。以下是一个例子：

// 读取JSON文件
QFile file("data.json");
if (file.open(QIODevice::ReadOnly)) {
    QJsonParseError error;
    QJsonDocument doc = QJsonDocument::fromJson(file.readAll(), &error);
    if (error.error == QJsonParseError::NoError && doc.isObject()) {
        QJsonObject obj = doc.object();
        QString name = obj.value("name").toString();
        int age = obj.value("age").toInt();
    }
    file.close();
}
// 写入JSON文件
QJsonObject obj;
obj.insert("name", "Tom");
obj.insert("age", 20);
QJsonDocument doc(obj);
QFile file("data.json");
if (file.open(QIODevice::WriteOnly)) {
    file.write(doc.toJson());
    file.close();
}
3.操作XML文件 XML是一种常用的文本格式，用于表示结构化的数据，在Qt中可以通过QXmlStreamReader类和QXmlStreamWriter类来读写XML文件。以下是一个例子：

// 读取XML文件
QFile file("data.xml");
if (file.open(QIODevice::ReadOnly)) {
    QXmlStreamReader reader(&file);
    while (!reader.atEnd()) {
        reader.readNext();
        if (reader.isStartElement() && reader.name() == "person") {
            QString name = reader.attributes().value("name").toString();
            int age = reader.attributes().value("age").toInt();
            // 处理读取到的数据
        }
    }
    file.close();
}
// 写入XML文件
QFile file("data.xml");
if (file.open(QIODevice::WriteOnly)) {
    QXmlStreamWriter writer(&file);
    writer.setAutoFormatting(true);
    writer.writeStartDocument();
    writer.writeStartElement("persons");
    writer.writeStartElement("person");
    writer.writeAttribute("name", "Tom");
    writer.writeAttribute("age", "20");
    writer.writeEndElement();
    writer.writeEndElement();
    writer.writeEndDocument();
    file.close();
}
以上是Qt中操作INI文件、JSON文件和XML文件的简单示例，通过这些方法，我们可以方便地读写和处理各种数据格式的文件。
```

21、HTTP协议、WebSocket协议？
22、QtChart(图表、曲线图、饼状图、柱形、拆线图等
23、Qt中音频类和视频类分别是什么？
24、QML鼠标与事件处理？？QML布局？Loader动态加载组件？

25、23种设计模式应用场景？
26、Qt相机和视频处理技术?
27、OpenCV人脸识别技术方法？
28、OpenCV实现图片美化原理机制？
29、OpenCV多图合成技术原理？
30、OpenCV的视频中反投影图像技术原理？

##  三、MySQL数据库技术20道题

1、数据库的常用范式有那些？
2、、MySQL架构的Server层的执行过程？
3、常用存储引擎？InnoDB与MyISAM的区别？
4、事务的ACID与实现原理？
5、数据库中的锁机制？
6、MySQL索引I的实现原理？
7、SQL优化和索引I优化、表结构优化？
8、数据库参数优先？
9、explain的执行计划?
10、MySQL的主从复制？
11、读写分离？
12、分库分表（垂直分表、垂直分库、水平分表、水平分库）？
13、分区？
14、主键一般用自增ID还是UUID？
15、视图View?
16、存储过程procedure?
17、触发器Trigger？
18、游标Cursor？