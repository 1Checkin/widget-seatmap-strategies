# widget-seatmap-strategies
Виджет показывает интерфейс выбора стратегий автоматической рассадки пассажиров,
показывает на примере какие места будут выбраны при изменении стратегий

- widget.js - сам виджет
- widget-ru.txt - шаблон по умолчанию на русском языке
- widget-en.txt - шаблон по умолчанию на английском языке
- euroset.html - пример интеграции виджета в страничку

*Интеграция виджета в HTML-код страницы*

```
<div id="container"></div>
<script type="text/javascript" src="path/to/widget.js"></script>
<script type="text/javascript">
document.addEventListener('DOMContentLoaded', function() {
    window.widget = new onecheckin_widget_seatmap_strategies(
        document.getElementById('container'), {
            "psg_count": 3,
            "onchange": function(strategies) {
                console.log(strategies)
            },
            "template_url": "https://static.1check.in/seatmap-widget-template.html"
            "template": ""
        }
    );
}, false);
</script>
```


*Параметры вызова*

- `psg_count` - количество пассажиров в заявке
- `onchange` - функция, которая будет вызываться каждый раз при изменении
стратегий
- `template_url` - URL файла с шаблонами для виджета (в случае если удобнее
дозагрузить)
- `template` - ID HTML элемента содержащего шаблон виджета, например

```
<script type="text/x-template" id="seatmap-widget">
</script>
```

