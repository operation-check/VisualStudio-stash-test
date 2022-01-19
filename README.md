# SBT製マニュアル確認
SBT製マニュアルについて「スタッシュの説明内容が気になったため」の調査用。

Visual Studioには元々本来のstush機能はなく、
ブランチ切り替えを行ったときに「コミット」していない場合にその変更が残ったまま切り替えを行うと、
この時切り替え先のブランチとコンフリクトが発生した場合に「一時退避をするか無視するか」の選択が出る。

コミットしていない段階ですでに事故である可能性が高いが、この時の「一時退避」選択をSBTはstashとして説明している。

### 確認としては

1.リポジトリを作成

2.リポジトリのクローン

3.ローカルでブランチを切る

4.リモートでもブランチを切る（切らなくても良いが保険）

5.プル（リモートにもあるブランチでないとできない）

6.ローカルで変更⇒コミットしないままブランチを切り替える

7.stushのような「一時退避」発生。

というのが調査の流れ。

※結論としてはVisualStudioにstushはなく、使いたい場合はコンソール（CLI）を利用したほうが堅実であること。
　ブランチ切り替え前にコミットするか、CLIでスタッシュするか、別ウィンドウでVisualStudioをもう一つ立ち上げることを推奨する。
