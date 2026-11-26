# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：[glossary_search_glossary]
- STEP 2 の [tool call]：glossary_search_glossary({'query': '3レベル'})
- STEP 3 の [tool call]：fetch_fetch({'url': 'https://modelcontextprotocol.io/'})
- STEP 4 の [tool call]：aws_aws___search_documentation({'search_phrase': 'Amazon S3 バージョニング 概要'})、aws_aws___search_documentation({'search_phrase': '"Using versioning" Amazon S3 overview', 'topics': ['general']})
- 気づき・疑問：MCPを複数登録した場合、質問に応じてモデルが適切なMCPを選択してくれる。

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎 
- やったこと：サーバーに「server.tool()(tools.search_glossary)」を追記
- 結果：エージェント側を変えなくても、一覧で使えるツールが増え、質問で呼ばれた。
- 気づき・疑問：サーバーにツールを足しても、エージェントに接続先を設定してもモデルに渡る情報は変わらない。理由はモデルはツール名・説明文・引数を読んでツールを選んで返答を利用しているのでツールの中身自体は見ていないため。そのため、ツールの危険性をモデルが判断することはできないので、ツール設定前には人間が確認する必要がある。
