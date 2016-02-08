SAE PHP dotenv
==========

SAE PHP dotenv是一个适配SinaAppEngine的PHP dotenv，修改自Vance Lucas的[PHP dotenv](https://github.com/vlucas/phpdotenv)。
唯一的改动是把SAE禁用的函数putenv()注释掉（在src/Loader.php的第341行和第372行）。
因为dotenv同时使用putenv,$_ENV和$_SERVER方法注册变量，因而注释之后不影响使用，
依然可以继续用getenv(),env()等函数。


那，为什么要这么做？
---------
PHP程序慢慢地在向模块化的方向发展，整个程序构建在其他人提供的各种模块之上。
为了能在SAE上使用PHP dotenv的模块以及使用基于PHP dotenv的一些应用（比如 Laravel),
需要一个不使用putenv函数的dotenv，于是有了这个。

欢迎任何意见及建议。