# TRUNK 技術面談のテーマ

本リポジトリは、TRUNK 株式会社エンジニア採用のための技術面談のテーマになります。
弊社の採用情報につきましては、[TRUNK 株式会社 採用情報](https://trunk.company/#recruit)をご覧ください。

# TRUNK について

数ある企業の中から、TRUNK 株式会社にご興味をお持ちいただきありがとうございます。
弊社は、

「生まれた環境に関係なく、
やる気次第で誰でも活躍できる
世界をつくる。」

というビジョンを掲げ、人の生活に大きく関わってくる「働く」という活動全般の領域を市場として、教育と採用のプロダクト作りにチャレンジしています。
あなたのスキルやキャリアを活かして、弊社のプロダクト作りにご参画いただくことを心よりお待ちしております。

# テーマ

学習システムの学習コンテンツ管理がテーマとなります。
以下の要件を読んで、実装の計画を立ててください。

本内容に正解があるとは考えておらず、弊社エンジニアと楽しく議論できることを願っています。


### データ構造

- 学習コンテンツ: テキストと２つの問題が含まれます。
- 問題: ４つの選択肢の中から正しいものを選ぶ問題

以下、学習コンテンツの例になります。

```json
{
    "id": 1,
    "title": "TypeScriptの基本",
    "text": "TypeScriptとは、JavaScriptに型を追加した言語です。型を追加することで、開発体験を向上させることができます。...",
    "questions": [
        {
            "id": 1,
            "text": "TypeScriptは何言語の拡張ですか？",
            "choices": [
                {"id": 1, "text": "JavaScript", "isCorrect": true},
                {"id": 2, "text": "Python", "isCorrect": false},
                {"id": 3, "text": "Java", "isCorrect": false},
                {"id": 4, "text": "C#", "isCorrect": false},
            ]
        },
        {
            "id": 2,
            "text": "TypeScriptの開発元はどこですか？",
            "choices": [
                {"id": 1, "text": "Google", "isCorrect": false},
                {"id": 2, "text": "Microsoft", "isCorrect": true},
                {"id": 3, "text": "Apple", "isCorrect": false},
                {"id": 4, "text": "Facebook", "isCorrect": false},
            ]
        }
    ]
}
```

### 要件

管理者と受講生の2種類のユーザーが存在し、それぞれ以下の操作ができます。

* 管理者は学習コンテンツを作成、閲覧、編集、公開、回答閲覧　をすることができます。
  * 公開したあとコンテンツを編集することができますが、*その変更は現在公開中のコンテンツには反映されません*。

* 受講生は学習コンテンツを閲覧、問題への回答することができます。
  * ただし、学習コンテンツが公開されるまでは、閲覧、問題への回答はできません。
  * 公開されているコンテンツのみ、閲覧、問題への回答ができます。

例えば、データの例の「TypeScriptの基本」という学習コンテンツを一度公開したあと、
タイトルを「TypeScriptの基本」から「はじめてのTypeScript」に変更したとします。
この場合、受講生が閲覧できるのは、「TypeScriptの基本」になります。
再度、公開することで、「はじめてのTypeScript」を受講生が閲覧できるようになります。

管理画面からの受講生の回答閲覧は、学習コンテンツごとにすべての回答を閲覧できるようにする必要があります。

### 実装の計画

上記要件のもと、どう実装するか考えてください。


事前にテキストでご提出頂ける場合は、RDBMSのスキーマやAPIなどを含め、MarkdownやYAMLのような簡単なテキスト形式でご提出お願いいたします。

複数の方法がある場合は、メリットとデメリットを議論できると嬉しいです。


# お問い合わせ先

なにかご不明な点やご質問などございましたら、[お問い合わせ](https://www.work-school.com/contact) よりお気軽にお問い合わせください。
