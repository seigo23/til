## groupingsの中ではransackable_scopeは使えない
- 下記の場合、some_ransackable_scopeが`Model`でransackable_scopesに登録されていても使えない
- 多分ransackの不具合？？

```ruby

param1 = { some_ransackable_scope: true }

param2 = {id_not_null: true, id_not_eq: 0}

@model = Model.ransack(g:[param1, param2])
```


- なので、groupingsを使いたい場合は別で検索をかけることでとりあえず対応した
- ransackable_scopes以外の検索条件では絞れてるので、パラメータに入ってる場合は特別に対応する（さらに絞る）

```ruby
# さっきの続き

# some_ransackable_scopeがModelでscope登録してある前提
if params[:q] && params[:q]["some_ransackable_scope"]
  @model = Model.some_ransackable_scope
end

```
