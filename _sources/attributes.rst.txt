Element attributes
==================

How to get, set, check for, and remove attributes with vanilla JavaScript.

.. code-block:: html

  <a class="link"
     data-name="Google"
     href="https://www.google.com"
     id="search"
     title="Google search"
     >Link</a>


Get attribute
-------------

.. code-block:: javascript

  let link = document.getElementById('search')

  // get an attribute
  let title = link.getAttribute('title')

  // get a data attribute
  let name = link.getAttribute('data-name')



Set attribute
-------------

.. code-block:: javascript

  let link = document.getElementById('search')

  // set an attribute
  let title = link.setAttribute('title', 'Go to Google.com')

  // set a data attribute
  let name = link.setAttribute('data-name', 'Google.com')



Check for attribute
-------------------

.. code-block:: javascript

  let link = document.getElementById('search')

  if (!link.hasAttribute('aria-describedby')) {
      console.log('No ARIA described by')
  }



Remove attribute
----------------

.. code-block:: javascript

  let link = document.getElementById('search')

  // remove an attribute
  link.removeAttribute('title')

  // remove a data attribute
  link.removeAttribute('data-name')



Data attributes
---------------

Data attributes are custom attributes on an element that start with ``data-``.


Accessing
^^^^^^^^^

The ``HTMLElement.dataset`` property is an easy way to get/set data attributes.

.. code-block:: html

  <a class="modal-link"
     data-current="8"
     data-target="#dialog"
     data-toggle="modal"
     href=""
     >Open dialog</a>


.. code-block:: javascript

  let link = document.querySelector('a.modal-link')

  // get all the data attributes as key/value pairs
  let data = link.dataset
  // data = {current: 8, target = "#dialog", toggle = "modal"}

  // get individual attribute values
  let target = link.dataset.target
  let current = link.dataset['current']

  // get multiple attribute values at once
  let {current, target} = link.dataset

  // set individual attribute values
  link.dataset.current = 18



CSS Selectors
^^^^^^^^^^^^^

Style with CSS

.. code-block:: css

  /**
   * Style a toggle button
   */
  [data-toggle] {
    border: 1px solid blue;
    font-size: 0.8em;
  }


Select elements in JavaScript

.. code-block:: javascript

  let item = document.querySelector('[data-toggle]')

  // check if an element has a data attribute
  if (item.matches('[data-toggle]')) {
    console.log('item can toggle things')
  }


`Additional ways to use data attributes for selecting elements <https://gomakethings.com/attribute-selectors-in-css/>`_
