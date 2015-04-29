Examples
========
For working examples checkout http://joetsoi.github.com/flot-barnumbers/

Usage
=====
simple flot plugin to draw bar numbers in bars, simply add

    series: {
        bars: {
            numbers: {
                show : boolean
            }
        }
    }

The below will continue to work for now to prevent breaking of existing code

    series: {
        bars: {
            showNumbers: boolean
        }
    }

## Options for positioning

    series: {
        bars: {
            numbers: {
                xAlign: function or number,
                yAlign: function or number,
            }
        }
    }

By default numbers will be positioned in the center of the bars, you can
specify a function or a number to override this behaviour. If you have a
horizontal bar chart, these 2 functions will switch round the axes they
are working on.

## Formatting the numbers

    series: {
        bars: {
            numbers: {
                formatter: function,
            }
        }
    }

You can pass in a function that taking the first argument as the original number that would have been displayed. You can then manipulate it however you wish and return it.  Example:

```
    series: {
        bars: {
            numbers: {
                formatter: function(v) {
                    return Math.ceil(v) + "%";
                },
            }
        }
    }
```

Todo
====
* currently breaks at series.bars.align : "center"
