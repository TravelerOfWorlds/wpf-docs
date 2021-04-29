---
layout: post
title: Tick Lines | Axis | SfChart | WPF | Syncfusion 
description: This section explains about chart axis major tick lines, minor tick lines, positioning the tick lines and its customization in WPF chart
platform: wpf
control: SfChart
documentation: ug
---

# Tick lines in WPF Chart

Tick lines are the small lines which is drawn on the axis line representing the axis labels. Tick lines will be drawn outside of the axis by default. 

## Major tick lines

By default, major tick lines are automatically added to the [`ChartAxis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#) in its defined intervals to representing axis labels.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300" Palette="BlueChrome">

<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis />
</chart:SfChart.PrimaryAxis>
          
<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis/>
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:ColumnSeries ItemsSource="{Binding NumericData}" XBindingPath="XValue" YBindingPath="YValue"/>
</chart:SfChart.Series>
        
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis();
chart.SecondaryAxis = new NumericalAxis();

ColumnSeries series = new ColumnSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

## Major tick line size

Tick lines thickness can be customized using [`TickLineSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_TickLineSize) property as shown in the below code snippet.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300" Palette="BlueChrome">

<chart:SfChart.Resources>
<Style TargetType="Line" x:Name="lineStyle">
<Setter Property="Stroke" Value="Red"/>
</Style>
</chart:SfChart.Resources>

<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis TickLineSize="10" ShowGridLines="False" MajorTickLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.PrimaryAxis>
          
<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis/>
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:ColumnSeries ItemsSource="{Binding NumericData}" XBindingPath="XValue" YBindingPath="YValue"/>
</chart:SfChart.Series>
        
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
   TickLineSize = 10,
   ShowGridLines = false,
   MajorTickLineStyle = chart.Resources["lineStyle"] as Style     
};

chart.SecondaryAxis = new NumericalAxis();

ColumnSeries series = new ColumnSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![TickLineSize support in WPF Chart](Axis_image/WPF_Chart_Axis_TickLineSize.png)

## Positioning the major tick lines

Tick lines can be positioned inside or outside of the chart area using [`TickLinesPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_TickLinesPosition) property. By default the tick lines will positioned outside of the chart area. The following code example demonstrates the positioning tick lines inside chart area.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300"  Palette="BlueChrome">

<chart:SfChart.Resources>
<Style TargetType="Line" x:Name="lineStyle">
<Setter Property="Stroke" Value="Red"/>
</Style>
</chart:SfChart.Resources>

<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis Interval="1"  ShowGridLines="False" TickLinesPosition="Inside" TickLineSize="10" MajorTickLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.PrimaryAxis>
           
<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis/>
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:ColumnSeries ItemsSource="{Binding NumericData}" XBindingPath="XValue" YBindingPath="YValue"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
   Interval = 1,
   ShowGridLines = false,
   TickLineSize = 10,
   TickLinesPosition = AxisElementPosition.Inside,
   MajorTickLineStyle = chart.Resources["lineStyle"] as Style    
};

chart.SecondaryAxis = new NumericalAxis();

ColumnSeries series = new ColumnSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Major tick lines positioning in WPF Chart](Axis_image/WPF_Chart_Axis_Positioning_MajorTickLines.png)

## Style for major tick lines

Style can be applied to major tick lines using [`MajorTickLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_MajorTickLineStyle) property. The following code snippet demonstrates the styling of major tick lines.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300" Palette="BlueChrome">
           
<chart:SfChart.Resources>
<Style TargetType="Line" x:Name="lineStyle">
<Setter Property="StrokeThickness" Value="1"/>
<Setter Property="Stroke" Value="Red"/>
</Style>
</chart:SfChart.Resources>

<chart:SfChart.PrimaryAxis>
<chart:CategoryAxis Interval="1" ShowGridLines="False" TickLineSize="10" MajorTickLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis/>
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:ColumnSeries ItemsSource="{Binding NumericData}" XBindingPath="XValue" YBindingPath="YValue"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new CategoryAxis()
{
    Interval = 1,
    ShowGridLines = false,
    TickLineSize = 10,
    MajorTickLineStyle = chart.Resources["lineStyle"] as Style    
};

chart.SecondaryAxis = new NumericalAxis();

ColumnSeries series = new ColumnSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Major tick lines customization support in WPF Chart](Axis_image/WPF_Chart_Axis_Customize_MajorTickLines.png)

## Minor tick lines

Minor tick lines can be added by defining [`SmallTicksPerInterval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.RangeAxisBase.html#Syncfusion_UI_Xaml_Charts_RangeAxisBase_SmallTicksPerInterval) property. This property will add the tick lines to every interval.

The following code example demonstrates the small ticks set for every interval.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300" Palette="BlueChrome">

<chart:SfChart.Resources>
<Style TargetType="Line" x:Name="lineStyle">
<Setter Property="Stroke" Value="Red"/>
</Style>
</chart:SfChart.Resources>
           
<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis Interval="1" ShowGridLines="False" SmallTicksPerInterval="4" MinorTickLineStyle="{StaticResource lineStyle}" />
</chart:SfChart.PrimaryAxis>
           
<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis/>
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:ColumnSeries ItemsSource="{Binding NumericData}" XBindingPath="XValue" YBindingPath="YValue"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
    Interval = 1,
    ShowGridLines = false, 
    SmallTicksPerInterval = 4,
    MinorTickLineStyle = chart.Resources["lineStyle"] as Style      
};

chart.SecondaryAxis = new NumericalAxis();

ColumnSeries series = new ColumnSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Minor tick lines support in WPF Chart](Axis_image/WPF_Chart_Axis_MinorTickLines.png)

## Minor tick line size

The thickness of the minor tick lines can be customized using [`SmallTickLineSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.RangeAxisBase.html#Syncfusion_UI_Xaml_Charts_RangeAxisBase_SmallTickLineSize) property as shown in the below code snippet.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300" Palette="BlueChrome">

<chart:SfChart.Resources>
<Style TargetType="Line" x:Name="lineStyle">
<Setter Property="Stroke" Value="Red"/>
</Style>
</chart:SfChart.Resources>

<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis ShowGridLines="False" Interval="1" SmallTicksPerInterval="3" SmallTickLineSize="10" MinorTickLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.PrimaryAxis>
            
<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis />
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:SplineSeries ItemsSource="{Binding NumericData}" XBindingPath="XValue" YBindingPath="YValue"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
    Interval = 1,
    ShowGridLines = false,
    SmallTicksPerInterval = 3,
    SmallTickLineSize = 10,
    MinorTickLineStyle = chart.Resources["lineStyle"] as Style 
};

chart.SecondaryAxis = new NumericalAxis();

SplineSeries series = new SplineSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Minor tick line size in WPF Chart](Axis_image/WPF_Chart_Axis_Customize_MinorTickLines.png)

## Positioning the minor tick lines

Minor tick lines can be positioned inside or outside using [`SmallTickLinesPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.RangeAxisBase.html#Syncfusion_UI_Xaml_Charts_RangeAxisBase_SmallTickLinesPosition) property. By default the minor tick lines will be positioned outside.

The following code example demonstrates the positioning of minor tick lines inside the chart area.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300"  Palette="BlueChrome">

<chart:SfChart.Resources>
<Style TargetType="Line" x:Name="lineStyle">
<Setter Property="Stroke" Value="Red"/>
</Style>
</chart:SfChart.Resources>
            
<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis Interval="1" ShowGridLines="False" SmallTicksPerInterval="5" 
 SmallTickLinesPosition="Inside" MinorTickLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.PrimaryAxis>
           
<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis/>
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:SplineSeries ItemsSource="{Binding NumericData}" XBindingPath="XValue" YBindingPath="YValue"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
    Interval = 1,
    ShowGridLines= false,           
    SmallTicksPerInterval = 5,
    SmallTickLinesPosition = AxisElementPosition.Inside,
    MinorTickLineStyle = chart.Resources["lineStyle"] as Style 
};

chart.SecondaryAxis = new NumericalAxis();

SplineSeries series = new SplineSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Minor tick lines positioning support in WPF Chart](Axis_image/WPF_Chart_Axis_Positioning_MinorTickLines.png)

## Style for minor tick lines

Minor tick lines can be customized by using [`MinorTickLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_MinorTickLineStyle) property. The following code example and image demonstrates the style for minor tick lines.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300" Palette="BlueChrome">

<chart:SfChart.Resources>
<Style TargetType="Line" x:Name="lineStyle" >
<Setter Property="StrokeThickness" Value="0.5"/>
<Setter Property="Stroke" Value="Red"/>
</Style>
</chart:SfChart.Resources>

<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis Interval="1" ShowGridLines="False"  FontSize="12" SmallTicksPerInterval="3" TickLineSize="10" SmallTickLineSize="5" MinorTickLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.PrimaryAxis>
            
<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis />
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:SplineSeries ItemsSource="{Binding NumericData}" XBindingPath="XValue" YBindingPath="YValue"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
    Interval = 1,
    ShowGridLines = false,
    FontSize = 12,
    SmallTicksPerInterval = 3,
    TickLineSize = 10,
    SmallTickLineSize = 5,
    MinorTickLineStyle = chart.Resources["lineStyle"] as Style    
};

chart.SecondaryAxis = new NumericalAxis();

SplineSeries series = new SplineSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "XValue";
series.YBindingPath = "YValue";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![MinorTickLineStyle customization support in WPF Chart](Axis_image/WPF_Chart_Axis_MinorTickLineStyle.png)

N> For category axis, small tick lines is not applicable since it is rendered based on index positions.
