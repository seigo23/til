# チェックボックスにvisible:falseしても押せない時
- `check("locator", visible: false)`でチェックボックスを下記みたいなエラーが出てチェックできない時
- `Unable to find visible checkbox "locator" that is not disabled`
- こんな感じでいける
- `find("#locator", visible: false).click`
- 参考：https://stackoverflow.com/questions/35874291/unable-to-find-checkbox-with-capybara
