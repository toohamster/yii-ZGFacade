# yii-ZGFacade
使用简单的方式来省掉视图模版页面顶部写类引用

## 你是否不想在模版页面顶部写太多 use 全路径的类声明语句,如果是,可以试试 yii-ZGFacade

```
Facade 包装类

优点:
    使用简单的方式来省掉视图里面长长的命名空间调用,诸如 YII 的模版
缺点:
    这么写在 IDE 中会失去代码自动提示的功能,对于 sublime 狗而言貌似不是缺点

使用方法:
    ZGFacade::{方法名}( {facade名称}, 参数1, 参数2,...参数n )

<code>
// 初始化
ZGFacade::setZGFacade('form', 'Aert_Form');
ZGFacade::setZGFacade('esClient', '\Elasticsearch\Client');

// 使用demo
$form = ZGFacade::newInstance('form', 'frm2', 'delete');
dump($form);

echo ZGFacade::server('form', 'REQUEST_METHOD');
echo ZGFacade::get('form', 'a');

  $dsn      = Config::get('esken.dsn');
  $esClient = ZGFacade::newInstance('esClient', $dsn);
  dump($esClient);
</code>
```