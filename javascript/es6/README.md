# Javascript ES6

## 개발환경
- [LINK](https://github.com/akageun/hello-es6)

## 소스

#### let, const

#### class

#### arrow function

#### Object.assign
- 두개의 Object를 병합할 때 사용

```javascript
    (function () {
        basic1();
        basic2();
    })();

    function basic1() {
        const src = {a: 1, b: 2};
        const rtnTarget = Object.assign({}, src);

        console.log(JSON.stringify(rtnTarget)); // {"a":1,"b":2}
    }

    function basic2() {
        const target = {a: 1, b: 2};
        const src = {b: 3, c: 4};

        const rtnTarget = Object.assign(target, src);

        console.log(JSON.stringify(target)); // {"a":1,"b":3,"c":4}
        console.log(JSON.stringify(rtnTarget)); // {"a":1,"b":3,"c":4}
    }
```

#### ... 