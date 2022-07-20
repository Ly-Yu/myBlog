---
title: 防抖 节流
date: 2022-07-18 09:34:27
tags:
---
防抖：点击执行函数，n秒后执行函数，如果在n秒内再次点击，则重新计算时间
节流：事件在n秒内被触发多次，函数只执行一次


## 防抖

#### 基本原理

```javascript
function debounce(fn,time) {
    let timer = null
    return (...args)=>{
        if(timer){
            clearTimeout(timer)
        }
        timer = setTimeout(()=>{
            fn.apply(this,args)
        },time)
    }
}
```

#### 使用方法

```javascript
const request = debounce(()=>{},3000)
```

## 节流

#### 基本原理
```javascript
       function throttle(fn, time) {
            let timer = null;
            return (...args) => {
                if (!timer) {
                    timer = setTimeout(() => {
                        fn.apply(this, args)
                        timer = null
                    }, time)
                }
            }
        }
```

#### 使用方法

```javascript
const request = debounce(()=>{},3000)
```