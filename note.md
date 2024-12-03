### 如何新增一個branch並且繼續commit?
```
git checkcout master~2 //回到上上一個commit
git checkout -b cat //在此處建立一個名為cat的branch -b 就是branch

!!!其實可以直接寫
git checkout -b cat master~2
```


### 如何清除最後一次commit
```
git reset master~
```

### 如何合併多個commit
```
git rebase -i <commit> // -i interactive 會把<commit>之後的commit都列出來，要合併就把 pick 改成 squash
```
