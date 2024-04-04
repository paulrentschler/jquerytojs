Working with CSS classes
========================

The `classList` property of an element allows for getting or modifying the CSS classes of the element.

.. code-block:: javascript

  let item = document.createElement('div')

  // add a class
  item.classList.add('test')

  // add multiple classes
  item.classList.add('apple', 'banana', 'grape')

  // remove a class
  item.classList.remove('test')

  // remove multiple classes
  item.classList.remove('test', 'apple', 'banana')

  // toggle a class
  item.classList.toggle('banana')

  // toggle class based on test condition
  item.classList.toggle('grape', item.shape == 'round')

  // determine if a class exists on an element
  item.classList.contains('apple')  // false
  item.classList.contains('banana')  // true

  // replace one class with another
  item.classList.replace('banana', 'test')


Docs: `element.classList property <https://developer.mozilla.org/en-US/docs/Web/API/Element/classList>`_
