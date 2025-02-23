---
title: Overview
page_title: Overview
description: "Learn the basics when working with the Telerik UI LinearGauge component for {{ site.framework }}."
previous_url: /helpers/gauges/lineargauge/overview
slug: overview_lineargaugehelper_aspnetcore
position: 1
---

# LinearGauge Overview

{% if site.core %}
The Telerik UI LinearGauge TagHelper and HtmlHelper for {{ site.framework }} are server-side wrappers for the Kendo UI LinearGauge widget.
{% else %}
The Telerik UI LinearGauge HtmlHelper for {{ site.framework }} is a server-side wrapper for the Kendo UI LinearGauge widget.
{% endif %}

The LinearGauge represents values on a linear scale.

* [Demo page for the LinearGauge HtmlHelper](https://demos.telerik.com/{{ site.platform }}/linear-gauge/index)
{% if site.core %}
* [Demo page for the LinearGauge TagHelper](https://demos.telerik.com/aspnet-core/linear-gauge/tag-helper)
{% endif %}

## Initializing the LinearGauge

The following example demonstrates how to initialize the LinearGauge.

```HtmlHelper
    @(Html.Kendo().LinearGauge()
        .Name("linearGauge") // The name of the LinearGauge is mandatory. It specifies the "id" attribute of the widget.
        .Scale(scale => scale
            .Min(0) // Set the min value of the LinearGauge.
            .Max(200) // Set the min value of the LinearGauge.
        )
        .Pointer(pointer => pointer
            .Value(10) // Set the value of the LinearGauge.
        )
    )
```
{% if site.core %}
```TagHelper
    <kendo-lineargauge name="gauge"></kendo-lineargauge>
```

## Basic Configuration

The LinearGauge configuration options are passed as attributes.

```HtmlHelper
    @(Html.Kendo().LinearGauge()
          .Name("gauge")
          .Pointer(pointer => pointer.Value(10))
          .Scale(scale => scale
              .MajorUnit(20)
              .MinorUnit(2)
              .Min(-40)
              .Max(60)
              .Ranges(ranges =>
              {
                  ranges.Add().From(-40).To(-20).Color("#2798df");
                  ranges.Add().From(30).To(45).Color("#ffc700");
                  ranges.Add().From(45).To(60).Color("#c20000");
              }
              )
          )
    )
```
```TagHelper
    <kendo-lineargauge name="gauge">
        <lineargauge-pointers>
            <pointer value="10"></pointer>
        </lineargauge-pointers>
        <scale major-unit="20" minor-unit="2" min="-40" max="60">
            <lineargauge-scale-ranges>
                <range color="#2798df" from="-40" to="-20">
                </range>
                <range color="#ffc700" from="30" to="45">
                </range>
                <range color="#c20000" from="45" to="60">
                </range>
            </lineargauge-scale-ranges>
        </scale>
    </kendo-lineargauge>
```
{% endif %}

## Referencing Existing Instances

To reference an existing Telerik UI LinearGauge instance, use the [`jQuery.data()`](https://api.jquery.com/jQuery.data/) configuration option. Once a reference is established, use the [LinearGauge client-side API](https://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/lineargauge#methods) to control its behavior.

        // Place the following after the LinearGauge for {{ site.framework }} declaration.
        <script>
        $(function() {
        // The Name() of the LinearGauge is used to get its client-side instance.
            var gauge = $("#linearGauge").data("kendoLinearGauge");
        });
        </script>

## See Also

* [Basic Usage of the LinearGauge HtmlHelper for {{ site.framework }} (Demo)](https://demos.telerik.com/{{ site.platform }}/linear-gauge/index)
{% if site.core %}
* [Basic Usage of the LinearGauge TagHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/linear-gauge/tag-helper)
{% endif %}
* [Server-Side API](/api/lineargauge)
