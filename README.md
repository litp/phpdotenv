SAE PHP dotenv
==========

SAE PHP dotenv是一个适配SinaAppEngine的PHP dotenv，修改自Vance Lucas的[PHP dotenv](https://github.com/vlucas/phpdotenv)。
唯一的改动是在使用SAE禁用的函数putenv()前，先判断是否存在该函数，如果不存在则不使用该函数，如果存在则不做任何变动。
因为dotenv同时使用putenv,$_ENV和$_SERVER方法注册变量，因而在禁用了putenv的服务器上之后不能使用getenv函数来获得相应的环境变量，但可以从全局变量$_ENV和$_SERVER中取得变量。


为什么要这么做？
---------
PHP程序慢慢地在向模块化的方向发展，整个程序构建在其他人提供的各种模块之上。
为了能在SAE上使用PHP dotenv的模块以及使用基于PHP dotenv的一些应用（比如 Laravel),
需要一个不使用putenv函数的dotenv，于是有了这个。

欢迎任何意见及建议。