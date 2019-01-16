# Handlebars.js : 핸들바
#### 링크
- Homepage : http://handlebarsjs.com/
- GitHub : https://github.com/wycats/handlebars.js/


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Handlebar Example</title>
</head>
<body>
<div id="result-entry-template"></div>
<hr>
<div id="result-helper-template"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.0.12/handlebars.min.js"></script>
<script id="entry-template" type="text/x-handlebars-template">
    <ul>
        {{#items}}
        <li>
            {{name}} - {{emotion}}
        </li>
        {{/items}}
    </ul>
</script>

<script id="helper-template" type="text/x-handlebars-template">
    <ul>
        {{#items}}
        <li>
            {{result_text}}
        </li>
        {{/items}}
    </ul>
</script>

<script>
    (function () {
        console.log("test2");
        entryTemplate();
        helperTemplate();
    })();

    function entryTemplate() {
        console.log("test");
        var source = document.getElementById("entry-template").innerHTML;

        var data = {
            items: [
                {name: "Handlebars", emotion: "love"},
                {name: "Mustache", emotion: "enjoy"},
                {name: "Ember", emotion: "want to learn"}
            ]
        };

        var template = Handlebars.compile(source);
        var html = template(data);

        console.log(data);

        document.getElementById("result-entry-template").innerHTML = html;
    }

    function helperTemplate() {
        var source = document.getElementById("helper-template").innerHTML;

        var data = {
            items: [
                {name: "Handlebars", emotion: "love"},
                {name: "Mustache", emotion: "enjoy"},
                {name: "Ember", emotion: "want to learn"}
            ]
        };

        Handlebars.registerHelper('result_text', function () {
            var emotion = Handlebars.escapeExpression(this.emotion),
                name = Handlebars.escapeExpression(this.name);

            return new Handlebars.SafeString(
                "<b>" + name + "</b>  " + emotion
            );
        });

        var template = Handlebars.compile(source);
        var html = template(data);

        document.getElementById("result-helper-template").innerHTML = html;
    }

</script>
</body>
</html>

```
