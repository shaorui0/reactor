

## test: ab

ab -n 10000 -c 32 http://127.0.0.1:8080/

### listen()

1. listen 的影响很大，
2. 内核调度的能力，即使只有一个thread。
    - backlog为1的话，需要每次将链接导入内核，其他的只能等待
    - 测试了1、10、100、10000 的区别
        - 10000 和 100的区别不大，也不是越大越好（具体还是硬件性能）
            - TODO 为什么？listen 的工作过程...
    - 那参数到底是多少？
    - 多线程有没有影响？

## ref doc


[blog: what is reactor](https://shaorui0.github.io/2020/12/16/python-generator-iterator-decorator/)


## TODO 


0. refactoring: class/function...
1. CGI: http://aosabook.org/en/500L/a-simple-web-server.html
2. 合到web server 中（lb 也是）