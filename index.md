---
layout: default
image: /assets/img/default_img.gif
---

<div class="header-container jumbotron">
    <div class="container">
        <h1>EXぜろちゃんねる</h1>
        <p>ぜろちゃんねるプラスからフォークされた、使いやすさと機能性を兼ね備えた５ちゃんねる風掲示板スクリプト。
        専用ブラウザと互換性があり、投稿の閲覧や書き込みが可能です。ぜろちゃんねるプラスからも簡単に移行できます。</p>
        <p><a class="btn btn-primary btn-lg" href="{{ "https://github.com/PrefKarafuto/ex0ch/releases/latest" | relative_url }}" role="button"><i class="fa fa-github"></i> Download v0.10.5</a></p>
    </div>
</div>

<div class="container">
    <div class="row">
        <div class="col-md-6">
            <h2 class="header-light regular-pad">EXぜろちゃんねるとは?</h2>
              <p class="lead">EXぜろちゃんねる（ex0ch）は、２ちゃんねる・５ちゃんねるライクの<a href="https://w.wiki/EeLC">スレッドフロート型掲示板</a>スクリプトです。簡単に導入でき、多彩な機能を兼ね備え、面倒な荒らし対策も強力な機能で対応できます。
              小規模なコミュニティから大規模掲示板群まで、柔軟な構築が可能です。もちろんスマートフォンからの閲覧にも対応し、5ch専用ブラウザも利用できます。
              プラグインを使った機能の拡張も可能です。</p>
              <p class="lead">EXぜろちゃんねるは<b>ぜろちゃんねるプラス</b>からフォークされたスクリプトですので、データの形式は殆ど同じであり、<code>ぜろちゃんねるプラスからEXぜろちゃんねるへの移行</code>は簡単です。ぜろちゃんねるプラスと同じようにアップデートし、管理画面を参照して足りないモジュールがあれば適宜追加してください。<b>確実なアップデート方法</b>は、先にEXぜろちゃんねるで掲示板を生成してからdatや各種設定ファイルを移行させるというやり方です。詳しくは<a href="/docs/home">ドキュメント</a>を参照してください。</p>
        </div>
        <div class="col-md-6 text-center">
            <img src="{{ "/assets/img/bbs_img.png" | relative_url }}" alt="ex0ch logo" class="img-responsive">
        </div>
    </div>
    <hr>
    <div class="row">
        <div class="col-sm-4">
            <h1 class="text-center"><i class="fa fa-pencil" aria-hidden="true"></i></h1>
            <h3 class="text-center">導入</h3>
            <p>詳細な手順については<a href="/docs/home">ドキュメント</a>を参照してください。</p>
            <p><b>要件</b></p>
            <p>CGIが実行可能な<code>Apache</code>サーバーと、<code title="･Perl使いを尊重する">Perl 5.16</code>以上が前提です。
            <a href="/docs/modules">必要なモジュール</a>がサーバーにあるか確認し、なければ<code>cpan</code>等でインストールしてください。</p>
            <p><b>必要モジュール一覧</b></p>
            <p>CGI</p>
            <p>JSON</p>
            <p>HTML::Entities</p>
            <p>XML::Simple</p>
            <p>LWP::UserAgent</p>
            <p>LWP::Protocol::https</p>
            <p>Net::SSLeay</p>
            <p>Net::DNS</p>
            <p>CGI::Cookie</p>
            <p>CGI::Session::ExpireSessions</p>
            <p><b>FastCGIを使う場合</b></p>
            <p>FCGI</p>
            <p><b>インストール方法</b></p>
            <p><a href="https://github.com/pref_karafuto/ex0ch">GitHub</a>から最新版をダウンロードし、解凍します。
            FTP転送ソフトを使って、解凍されたフォルダ内の<code>test</code>フォルダをアップロードします。
            完了したら、各フォルダ・ファイルにパーミッションを設定します。設定が終わったら<code>admin.cgi</code>にアクセスし、本体の設定を行なってください。</p>
        </div>
        <div class="col-sm-4">
            <h1 class="text-center"><i class="fa fa-cogs" aria-hidden="true"></i></h1>
            <h3 class="text-center">機能</h3>
            <p><b>管理</b></p>
            <p>掲示板を管理運営する上で避けて通れないのが<b>荒らし</b>の問題です。EXぜろちゃんねるでは特に荒らしへの対処能力に力を入れています。荒らし対策の第一義は、<b>そもそも書き込ませない</b>ことです。<code>正規表現を使ったNGワード</code>の登録や<code>IP、Host名、UserAgent、忍法帖IDによる規制</code>は勿論、スクリプトによる連投抑止のための<code>Captcha</code>や、プロキシ・VPN・Torなど匿名化された<b>不審なIP</b>を検出する<code>DNSBL・プロキシチェッカー</code>との連携機能が搭載されています。さらに、従来は<b>サーバー管理者が</b>逐一ハードコーディングするしかなかった<b>複雑な条件付き規制</b>を管理画面から設定できる新機能<code>BoardGuard DSL</code>により、強力なブロックが可能です。しかし、それでも障壁を突破する荒らしは出てしまうでしょう。そのために、条件に合致したレスやスレッドを一括で削除できる<code>レス検索＆削除</code>機能があります。たとえ<b>掲示板全体に</b>連投されたとしても削除に大きな労力はかかりません。</p>
            <p>ところで、荒らしをブロックするために規制を強くしてしまうと、荒らしではない<b>一般ユーザーの書き込みも</b>ブロックしてしまうケースが往々にしてあります。しかし、EXぜろちゃんねるでは、管理人が規制に引っかかった書き込みを確認し<code>追認して投稿</code>できる機能があります。これにより、荒らしに対してより的確な規制を実施することができるでしょう。</p>
            <p><b>利用</b></p>
            <p>EXぜろちゃんねるには、スレ主による<b>スレッドカスタム</b>の為の<code>ユーザーコマンド</code>があります。<b>設定で有効化されている場合</b>、例えば<code>名無しを変更</code>したり、あるいは<code>強制</code>したり、スレッドの<code>レス上限を拡張</code>したり、書き込みがあってもageないようにしたり、荒らしを<code>BAN</code>したりできます。標準搭載のコマンドはまだまだありますので、詳しくはドキュメントを参照してください。</p>
        </div>
        <div class="col-sm-4">
            <h1 class="text-center"><i class="fa fa-code-fork" aria-hidden="true"></i></h1>
            <h3 class="text-center">歴史</h3>
            <p><b>EXぜろちゃんねる(ex0ch)</b>は、元となる<b>ぜろちゃんねるプラス(0ch+)</b>の機能を拡充していこうというプロジェクトから出発しました。命名の<b>EX</b>とは<i>extreme,extended,expanded</i>などの意味合いを含ませたもので、plusのさらに先という事で名づけました。略称ex0chはimg0chに倣った名称です。<small>(※img0chとの互換性はありません)</small></p>
            <p>ぜろちゃんねるプラスは、大元の<b>ぜろちゃんねる(0ch)</b>スクリプトからフォークされ、スレッドフロート型の２ちゃんねる風掲示板スクリプトの代名詞としてとして広く普及していました。しかし、2013年のアップデートを最後に<b>開発の凍結</b>が宣言されており、新機能追加は望めない状態でした。
            そのような中で、メンテナンスの継続と便利な新機能を求める声の元、<b>利用者有志</b>により「ぜろちゃんねるプラス再開発プロジェクト」が始動し、名称を<code>EXぜろちゃんねる</code>として正式にリリースするに至りました。</p>
            <pre><code>2ch<br>└── 0ch<br>    ├── img0ch<br>    │   ├── php0ch<br>    │   └── mod0ch<br>    └── 0ch+<br>        └── ex0ch</code></pre>
            <p>本家ぜろちゃんねる開発者「精神衰弱 ◆kwSzvOHE」氏並びにぜろちゃんねるプラス開発者「windyakin ◆windyaking」氏を初めとする両スクリプトの開発陣の方々、そして再開発に協力して頂いた皆様に心からの謝意を表します。</p>
        </div>
    </div>
</div>
