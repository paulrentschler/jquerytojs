General JavaScript syntax
=========================

Looping
-------

forEach
^^^^^^^

.. code-block:: javascript

  const letters = ['a', 'b', 'c']

  letters.forEach((item) => {
    console.log(item)
  })



Working with numbers
--------------------

Ensure a value is an integer

.. code-block:: javascript

  x = "5"
  parseInt(x)


Round a number to the nearest multiple of `x`

.. code-block:: javascript

  function roundXlow(number)
  {
    // return the nearest multiple of x without exceeding number
    return Math.floor(number / x) * x
  }

  function roundXhigh(number)
  {
    // return the nearest multiple of x equal to or greater than number
    return Math.ceil(number / x) * x
  }

  function roundX(number)
  {
    // return the nearest multiple of x following normal rounding conventions
    return Math.round(number / x) * x
  }



Conditional tests for null/blank/false values
---------------------------------------------

This is "borrowed" directly from `StackOverflow <https://stackoverflow.com/a/27550756/645638>`_.

.. code-block:: javascript

  Null Test:

  if (variable === null)

  - variable = ""; (false) typeof variable = string
  - variable = null; (true) typeof variable = object
  - variable = undefined; (false) typeof variable = undefined
  - variable = false; (false) typeof variable = boolean
  - variable = 0; (false) typeof variable = number
  - variable = NaN; (false) typeof variable = number


  Empty String Test:

  if (variable === '')

  - variable = ''; (true) typeof variable = string
  - variable = null; (false) typeof variable = object
  - variable = undefined; (false) typeof variable = undefined
  - variable = false; (false) typeof variable = boolean
  - variable = 0; (false) typeof variable = number
  - variable = NaN; (false) typeof variable = number


  Undefined Test:

  if (typeof variable == "undefined")

  -- or --

  if (variable === undefined)

  - variable = ''; (false) typeof variable = string
  - variable = null; (false) typeof variable = object
  - variable = undefined; (true) typeof variable = undefined
  - variable = false; (false) typeof variable = boolean
  - variable = 0; (false) typeof variable = number
  - variable = NaN; (false) typeof variable = number


  False Test:

  if (variable === false)

  - variable = ''; (false) typeof variable = string
  - variable = null; (false) typeof variable = object
  - variable = undefined; (false) typeof variable = undefined
  - variable = false; (true) typeof variable = boolean
  - variable = 0; (false) typeof variable = number
  - variable = NaN; (false) typeof variable = number


  Zero Test:

  if (variable === 0)

  - variable = ''; (false) typeof variable = string
  - variable = null; (false) typeof variable = object
  - variable = undefined; (false) typeof variable = undefined
  - variable = false; (false) typeof variable = boolean
  - variable = 0; (true) typeof variable = number
  - variable = NaN; (false) typeof variable = number


  NaN Test:

  if (typeof variable == 'number' && !parseFloat(variable) && variable !== 0)

  -- or --

  if (isNaN(variable))

  - variable = ''; (false) typeof variable = string
  - variable = null; (false) typeof variable = object
  - variable = undefined; (false) typeof variable = undefined
  - variable = false; (false) typeof variable = boolean
  - variable = 0; (false) typeof variable = number
  - variable = NaN; (true) typeof variable = number

