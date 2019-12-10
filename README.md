# 08_09kadai マイ〇ビサイトの企業ページのスクレイピング概要

### 1. 前提条件  
言語はphpで、phpQueryというライブラリを使用。詳しいことは以下の公式ページより。  
<https://code.google.com/archive/p/phpquery/>

この公式からzipファイルをダウンロードして解凍。
その中のphpQuery-onefile.phpを使用する。  

### 2. 書き方  
基本的な扱い方はすでに先人の方々がQiita等に残してくださっているため、以下にいくつかサイトを残すのみとする。  
* 【php】webサイトから、欲しい情報を3行で取得する方法  
<https://qiita.com/dia/items/3cf963fa89b08b87e8ef>
* 【phpQuery】を使ってwebサイトをスクレイピングする  
<https://qiita.com/nadonado/items/0ac037d90c5248b7eac3>
* 【公式wiki】phpquery  
<https://code.google.com/archive/p/phpquery/wikis>

### 3. やっていることとファイル構成  
あらかじめ欲しい情報のDOMを下調べしておき、URLの一部（おそらく企業id）となっている部分を総当たりで調べていく。
今回は、id、業種、企業名、従業員数、本社住所、お問い合わせ、URLをターゲットとしている。
そして、その情報を一度csvファイルに格納してから、DBへの登録処理を行っている。  

課題で使っているファイルは、ブラウザから操作できるようにするのに、index.phpから検索する対象idを選択して、ScMynaviKadai.phpに遷移し処理が実行される。

#### ScMynaviKadai.phpについて
このファイルが実際のスクレイピングの処理、csvへの格納を行っている。