Packagist に公開されていない Composer パッケージをインストールするためのテストパッケージです。

このパッケージは Packagist に公開されていませんが、以下の手順で Composer を経由してインストールすることができます。

まず、パッケージをインストールしたいプロジェクトの `composer.json` に以下を追記します。

```json
{
  ...
  "repositories": [
    {
      "type": "github",
      "url": "https://github.com/okashoi/composer-hello-world"
    }
  ],
  ...
}
```

この状態で以下のコマンドを実行すればインストール完了です。

```basg
composer require okashoi/hello-world:dev-main
```

Composer のオートロード機能を経由して `sayHelloWorld()` 関数を利用できます。

```php
<?php

require_once __DIR__ . '/vendor/autoload.php';

use function Okashoi\sayHelloWorld;

echo sayHelloWorld(); // Hello, World.
```

## 参考

* [Libraries - Composer](https://getcomposer.org/doc/02-libraries.md#publishing-to-a-vcs)
* [The composer.json schema - Composer](https://getcomposer.org/doc/04-schema.md#repositories)
* [Repositories - Composer](https://getcomposer.org/doc/05-repositories.md)
