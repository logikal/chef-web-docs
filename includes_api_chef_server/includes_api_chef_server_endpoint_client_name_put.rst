.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.

The ``PUT`` method is used to update a specific |chef api client|. If values are not specified for the ``PUT`` method, the |chef server| will use the existing values rather than assign default values.

.. note:: ``PUT`` supports renames. If ``PUT /user/foo`` is requested with ``{ "name: "bar""}``, then it will rename ``foo`` to ``bar`` and all of the content previously associated with ``foo`` will be associated with ``bar``.

This method has no parameters.

**Request**

.. code-block:: xml

   PUT /organizations/NAME/clients/NAME

with a request body similar to:

.. code-block:: javascript

   {
     "name": "monkeypants",
     "private_key": true,
     "admin": false
   }

where ``private_key`` (when ``true``) will generate a new RSA private key for the |chef api client|. If ``admin`` is set to ``true`` the |chef api client| will be promoted to an admin |chef api client|.

**Response**

The response is similar to:

.. code-block:: javascript

   {
     "uri" : "https://chef.example/orgaizations/org1/clients/client1"
   }

**Response Codes**

.. list-table::
   :widths: 200 300
   :header-rows: 1

   * - Response Code
     - Description
   * - ``200``
     - |response code 200 ok|
   * - ``201``
     - |response code 201 created| (This response code is only returned when the client is renamed.)
   * - ``401``
     - |response code 401 unauthorized|
   * - ``403``
     - |response code 403 forbidden|
   * - ``404``
     - |response code 404 not found|
   * - ``409``
     - |response code 409 unauthorized| (This response code is only returned when a client is renamed, but a client already exists with that name.)
   * - ``413``
     - |response code 413 entity_too_large|
