Selecting DOM elements
======================

.. code-block:: html

  <html>
    <body>
      <div id="contents">
        <h1>Example</h1>

        <h2 class="subheading">Sub-example</h2>
        <p>Example, example</p>

        <h2 class="subheading">Sub-example Two</h2>
        <ul>
          <li><a href="">One</a></li>
          <li class="two"><a href="">Two</a></li>
          <li><a href="">Three</a></li>
        </ul>
      </div>
    </body>
  </html>


Using specific element attributes
---------------------------------

.. code-block:: javascript

  let contents = window.getElementById('contents')

  let listItems = window.getElementsByTagName('li')

  let subHeadings = window.getElementsByClassName('subheading')



Generic selector
----------------

.. code-block:: javascript

  // return only the first element that matches the selector
  let firstListItem = document.querySelector('#content ul li')

  // return NodeList of all elements that match the selector
  let listItems = document.querySelectorAll('#content ul li')

  // get all elements except something
  let mostItems = document.querySelectorAll('#content ul li:not(.two)')



Getting children
----------------

.. code-block:: javascript

  // using the children property
  let list = window.getElementByTagName('ul')
  let collection_of_list_items = list.children
  let array_of_list_items = Array.from(list.children)

  // using querySelectorAll
  let listItems = document.querySelectorAll('ul > li')

  // using nested selectors
  let list = document.querySelector('ul')
  let items = list.querySelectorAll('li')



Getting parent(s)
-----------------

.. code-block:: javascript

  // get the direct parent of an element
  let item = document.querySelector('li.two')
  let parent = item.parentNode  // returns the <ul> element

  // finding the first parent that matches a selector
  let item_link = document.querySelector('li > a')
  let list = item_link.closest('ul')

**Note:** ``closest()`` also checks the current element to see if it matches the criteria.
