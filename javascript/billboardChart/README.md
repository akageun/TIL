# BillBoard Chart
> D3 Wrapper Chart

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Billboard Chart</title>

    <!-- Load D3.js -->
    <script src="https://d3js.org/d3.v4.min.js"></script>

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/billboard.js/1.7.1/billboard.min.css"/>
</head>
<body>
<div id="chart"></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/billboard.js/1.7.1/billboard.min.js"></script>
<script>
    var chart = bb.generate({
        bindto: "#chart",
        data: {
            type: "bar",
            columns: [
                ["data1", 30, 200, 100, 170, 150, 250],
                ["data2", 130, 100, 140, 35, 110, 50]
            ]
        }
    });

</script>
</body>
</html>

```
