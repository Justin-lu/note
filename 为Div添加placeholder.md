# 为Div添加placeholder

今天开发的时候遇到这样一个问题，需要在edit-in-place文本编辑款为空得时候，显示placeholder，通常情况下，我们只需要在input框添加`placeholder="xxx"` 即可

```html
  <input type="text" placeholder="This is placeholder">
```

但是，由于使用了[edit-in-place](http://vitalets.github.io/x-editable/)插件，此时需要将`placehoder`添加到一个`DIV`上

通过搜索，在stackoverflow找到解决方法

```html
  <div contenteditable="true" name="description"  data-text="This is placeholder">```
```css
  [contenteditable=true]:empty:not(:focus):before{
    content:attr(data-text);
    color: #c4c3bc;
  }
```
