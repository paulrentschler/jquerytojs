Creating and Removing DOM elements
==================================

.. code-block:: html

  <html>
    <body>
      <div id="contents">
        <h1>Example</h1>

        <h2 class="subheading">Sub-example</h2>
        <p>Example, example</p>

        <h2 class="subheading">Sub-example Two</h2>
        <ul>
          <li>One</li>
          <li class="second">Two</li>
          <li>Three</li>
        </ul>
      </div>
    </body>
  </html>


Creating DOM elements
---------------------

.. code-block:: javascript

  let secondItem = document.querySelector('#contents ul li.second')

  // create a new list item
  let item = document.createElement('li')

  // add content
  item.innerHTML = 'Dynamically created item'

  // insert before the second item
  secondItem.parentNode.insertBefore(item, secondItem)

  // insert after the second item
  secondItem.parentNode.insertBefore(item, secondItem.nextSibling)

  // add the item to the end of the list
  secondItem.parentNode.appendChild(item)

  // clone a new item from another one (exact copy but separate references)
  let newItem = Object.assign({}, secondItem)
  newItem.classList.replace('second', 'fifth')
  secondItem.parentNode.appendChild(newItem)


Docs

- `node.appendChild(aChild) <https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild>`_
- `node.insertBefore(newNode, referenceNode) <https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore>`_


Removing DOM elements
---------------------

.. code-block:: javascript

  // remove a specific item
  let secondItem = document.querySelector('li.second')
  secondItem.parentNode.removeChild(secondItem)

  // remove all the list items
  let list = document.getElementByTagName('ul')
  Array.from(list.children).forEach((item) => {
    list.removeChild(item)
  })

