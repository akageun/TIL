# Javascript Basic

## if undefined
```javascript
    (function () {
        basicTest("");
        basic2Test("");
    })();

    function basicTest(testValue) {
        if (testValue === "") {
            console.log("basicTest : Empty");
        } else {
            console.log("basicTest :Not Empty");
        }
    }

    function basic2Test(testValue) {
        if (!testValue) {
            console.log("basic2Test :Empty");
        } else {
            console.log("basic2Test :Not Empty");
        }
    }
```