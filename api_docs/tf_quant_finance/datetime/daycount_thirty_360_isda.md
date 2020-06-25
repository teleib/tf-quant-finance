<!--
This file is generated by a tool. Do not edit directly.
For open-source contributions the docs will be updated automatically.
-->

*Last updated: 2020-06-17.*

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf_quant_finance.datetime.daycount_thirty_360_isda" />
<meta itemprop="path" content="Stable" />
</div>

# tf_quant_finance.datetime.daycount_thirty_360_isda

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/datetime/daycounts.py">View source</a>



Computes the year fraction between the specified dates.

```python
tf_quant_finance.datetime.daycount_thirty_360_isda(
    *, start_date, end_date, schedule_info=None, dtype=None, name=None
)
```



<!-- Placeholder for "Used in" -->

The 30/360 (ISDA / Bond Basis) convention specifies the year fraction
between the start and end date as the number of days by the following
formula between the two dates divided by 360.

  day difference = (Y2 - Y1) * 360 + (M2 - M1) * 30 + (D2 - D1)

where

  Y1 is the year, expressed as a number, of the start date;

  Y2 is the year, expressed as a number, of the end date;

  M1 is the calendar month, expressed as a number, of the start date;

  M2 is the calendar month, expressed as a number of the last date;

  D1 is the start date calendar day, unless such number would be 31, in
  which case D1 will be 30;

  D2 is the last date calendar day, unless such number would be 31 and D1
  is either 30 or 31, in which case D2 will be 30

Note that the schedule info is not needed for this convention and is ignored
if supplied.

#### For more details see:


https://en.wikipedia.org/wiki/Day_count_convention#30/360_Bond_Basis
https://www.isda.org/2008/12/22/30-360-day-count-conventions

#### Args:


* <b>`start_date`</b>: A `DateTensor` object of any shape.
* <b>`end_date`</b>: A `DateTensor` object of compatible shape with `start_date`.
* <b>`schedule_info`</b>: The schedule info. Ignored for this convention.
* <b>`dtype`</b>: The dtype of the result. Either `tf.float32` or `tf.float64`. If not
  supplied, `tf.float32` is returned.
* <b>`name`</b>: Python `str` name prefixed to ops created by this function. If not
  supplied, `thirty_360_isda` is used.


#### Returns:

A real `Tensor` of supplied `dtype` and shape of `start_date`. The year
fraction between the start and end date as computed by 30/360 convention.