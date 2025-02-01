Forms
=====

.. code-block:: html

  <form id="contact">
    <input type="hidden" name="source" value="website">

    <label for="name">Name</label>
    <input id="name" name="name" type="text" value="">

    <label for="email">Email</label>
    <input id="email" name="email" type="email" value="">

    <p>Are you a current customer?</p>
    <label>
      <input name="customer" type="radio" value="yes"> Yes
    </label>
    <label>
      <input name="customer" type="radio" value="no"> No
    </label>

    <label>
      <input name="mailinglist" type="checkbox" value="yes">
      Join our mailing list
    </label>

    <label for="reason">Why are you contacting us?</label>
    <select id="reason" name="reason">
      <option value="" hidden>--</option>
      <option value="question">I have a question</option>
      <option value="feedback">Provide feedback</option>
      <option value="complain">Complain incessantly</option>
    </select

    <label for="message">Your message</label>
    <textarea id="message" name="message"></textarea>
  </form>


Get/set field values
--------------------

.. code-block:: javascript

  let form = document.getElementById('contact')

  // select a particular input element
  let name = form.elements.name
  let reason = form.elements['reason']


  // get a particular field's value
  console.log(form.elements.email.value)


  // set a particular field's value
  form.elements.name.value = "Jane Smith"



Looping through fields
----------------------

``elements`` returns a ``HTMLFormControlsCollection`` which is array-like but cannot be looped over with linkgs like ``forEach`` or ``map``.

Convert it to an array, then you can loop through the elements.

.. code-block:: javascript

  let form = document.querySelector('form#contact')
  let fields = Array.from(form.elements)
  fields.forEach((field) => {
    console.log(field.name + ' = ' + field.value)
  })
