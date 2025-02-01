Manipulating DOM elements
=========================

Basics
------

.. code-block:: javascript

  let div = document.createElement('div')

  // add text content
  div.textContent = 'This only allows text, no HTML'

  // add HTML content
  div.innerHTML = 'This <b>allows</b> HTML tags'

  // add CSS class(es)
  div.className = 'new block'
  div.classList.add('new', 'block')

  // set/change the ID attribute
  div.id = 'unique-div'

  // set generic attributes
  div.setAttribute('data-type', 'new')

  // set CSS styling
  div.style.color = '#fff'
  div.style.backgroundColor = 'black'


Additional information

* :doc:attributes
* :doc:cssclasses



Adding to existing HTML
-----------------------

Initial HTML

.. code-block:: html

  <ul class="menu">
    <li>
      <input type="checkbox" value="one" />
    </li>
  </ul>


The **wrong** way to add to the list item

.. code-block:: javascript

  let item = window.querySelector('.menu li')
  item.innerHTML += '<span>First option</span>'

This will remove any event listeners associated with the content of the list item (i.e., an onClick event on the checkbox)


The **right** way to add to the list item

.. code-block:: javascript

  let item = window.querySelector('.menu li')
  let label = '<span>First option</span>'
  item.insertAdjacentHTML('beforeend', label)


