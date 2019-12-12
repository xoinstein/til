```shell
php -r 'echo date("Ymd", strtotime("+1 month", strtotime("2019-03-31"))) . "\n";'
20190501
```

strtotime 在处理 *+1 month* 这种情况时:

- 1.先做 +1 month，03-31加一个月就是 04-31
- 2.再做日期规范化，4月没有31号，所以就是05-01

解决方案，用"first day of"、"last day of" 修饰

```shell
php -r 'echo date("Ymd", strtotime("last day of +1 month", strtotime("2019-03-31"))) . "\n";'
20190430
```

