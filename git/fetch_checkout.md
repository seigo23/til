## リモートブランチからブランチを派生させる時の注意
- まずfetchしてリモート追跡を最新化する
- `git checkout -b branch_a origin/branch_a`ってやってリモート追跡の内容をローカルブランチに作る
- その後、`git checkout -b branch_b`ってすればbranch_aから派生したbranch_bが作れる
- その際に`git checkout -b branch_b origin/branch_a`みたいに直接リモート追跡から新しいブランチを作ろうとしたら、
関係ないファイルがステージングされてたり、よく分からないことになったので順をおってやる事
- 原因はまた調べとく

