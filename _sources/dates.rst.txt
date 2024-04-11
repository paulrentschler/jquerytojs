Dates
=====

Get the current date/time
-------------------------

.. code-block:: javascript

  let now = new Date()
  let month = now.getMonth() + 1
  let day = now.getDate()
  let year = now.getFullYear()
  let hour = now.getHours()
  let minutes = now.getMinutes()
  let seconds = now.getSeconds()

  alert('Current date/time: ' + year + '-'
                              + ((month < 10) ? '0': '') + month + '-'
                              + ((day < 10) ? '0' : '') + day + ' '
                              + hour + ':' + minutes + ':' + seconds)

Notes:

* `.getMonth()` returns a zero-based number
* `.getDate()` returns the day of the month (0-31)
* `.getDay()` returns the day of the week (0-6, 0 == Sunday)
