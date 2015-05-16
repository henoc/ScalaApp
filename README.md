# README

Stone言語の変形版  
自分の学習用

## 例文
### フィボナッチ数列
    let fib n = {
      if (n == 0) {
        0
      } else {
        if (n == 1) {
          1
        } else {
          (fib (n - 1)) + (fib (n - 2))
        }
      }
    }
    fib 10
### unless構文(マクロ)
    let macro unless cond thenBlock = {
      if (cond == 0) thenBlock
    }
### 独自の変数定義構文(マクロ)
    let macro def symbol literal = {
      let symbol = literal
    }
### for構文(マクロ)
    let macro for init cond each body = [
      init
      while (cond) {
        body
        each
      }
    ]
#### 使用例
    for {let i = 0} (i < 10) (i <- i + 1) {
        println i
    }
### HSP風のrepeat構文(アナフォリックマクロ)
    let macro repeat bound body = [
      let cnt = 0
      while (cnt < bound) {
        body
        cnt <- cnt + 1
      }
    ]
