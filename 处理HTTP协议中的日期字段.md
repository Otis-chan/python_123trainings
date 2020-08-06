```python
import sys
import datetime

def parse_http_datetime(s):
    if "-" in s:
        return datetime.datetime.strptime(s, "%A, %d-%b-%y %H:%M:%S %Z")
    elif s[-1] == "T":
        return datetime.datetime.strptime(s, "%a, %d %b %Y %H:%M:%S %Z")
    else:
        return datetime.datetime.strptime(s, "%a %b  %d %H:%M:%S %Y")


while True:
    line = sys.stdin.readline()
    line = line.strip()
    if line == '':
        break
    print(parse_http_datetime(line))
```

##### 要点：

1.python中时间日期格式化符号

2.

```python
datetime.datetime.strptime() 
```

输入的日期和时间为字符串形式，需要进一步处理日期和时间 → str转换为datetime

根据自行规定输入模式，将字符串信息转化为datetime格式