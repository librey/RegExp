# RegExp
常用正则表达式

## 正则表达式中的特殊字符

* `^` 前缀匹配，匹配字符串必须在最开始
```javascript
/^A/.test('Ana');//=>true
/^A/.test('anA');//=>false
```

* `$` 后缀匹配，匹配的字符串必须在最末尾
```javascript
/A$/.test('aaA');=>true
/A$/.test('Aaa');=>false
```

* `^$` 完全匹配，匹配的字符串必须和给定的表达式完全一致
```javascript
/^AAA$/.test('AAA');//=>true
/^AAA$/.test('AAAA');//=>false
```

## 一些常用表达式
金额验证(可以有两位小数): \d+(\.\d{0,2})?  
手机号码验证: 1[34578]\d{9}  
网络链接: (h|H)(r|R)(e|E)(f|F)\*=\*('|")?(\w|\\|\/|\.)+('|"|\*|>)?  
邮件地址: \w+([-+.]\w+)\*@\w+([-.]\w+)\*\.\w+([-.]\w+)\*  
图片链接: (s|S)(r|R)(c|C)\*=\*('|")?(\w|\\|\/|\.)+('|"|\*|>)?  
IP地址: (\d+)\.(\d+)\.(\d+)\.(\d+)  
中国手机号码: (86)\*0\*13\d{9}  
中国固定电话号码: (\(\d{3,4}\)|\d{3,4}-|\s)?\d{8}  
中国电话号码（包括移动和固定电话）: (\(\d{3,4}\)|\d{3,4}-|\s)?\d{7,14}  
中国邮政编码: [1-9]{1}(\d+){5}  
中国身份证号码: \d{18}|\d{15}  
整数: \d+  
浮点数（即小数）: (-?\d\*)\.?\d+  
任何数字: (-?\d\*)(\.\d+)?  
中文字符串: [\u4e00-\u9fa5]\*  
双字节字符串(汉字): [^\x00-\xff]\*  

### 手机号正则
中国大陆：开头1 3-8号段，后边跟9位数字  
台湾：09开头后面跟8位数字  
香港：9或6开头后面跟7位数字  
澳门：66或68开头后面跟5位数字  
大陆+港澳台手机正则 /^(([1][3-8]\d{9})|([69]\d{7})|([0][9]\d{8})|([6][86]\d{5}))$/
