Events
======

Doing work on page load
-----------------------

.. code-block:: javascript

  window.addEventListener('load', (event) => {
    alert('EVERYTHING on the page, including images, is loaded!')
  })

  window.addEventListener('DOMContentLoaded', (event) => {
    alert('DOM contents have been loaded, but not necessarily all the page dependencies')
  })



Types of events
---------------

* `input`: any change made in the text content (might want to debounce this)
* `change`:
  * if it is an `<input />`: change + lose focus
  * if it is an `<select>`: change option

