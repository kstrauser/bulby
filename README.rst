bulby
=================
Python library for managing the phillips hue lightbulb

Getting Started
=================
To get started you can get a list of your lights and work with them:

.. code-block:: python

    from bulby.client import HueBridgeClient
    client = HueBridgeClient()
    light = client.get_lights()[0]
    client.set_color(light.light_id, '00ff00')

and now your light should be green! You can also reference lights by name:

.. code-block:: python

    from bulby.client import HueBridgeClient
    client = HueBridgeClient()
    client.set_color('Office 1', '00ff00')

The first time you connect to a bridge, the username you specify (default ``bulbyappdev``) will be created on that bridge.

.. code-block:: python

    from bulby.client import HueBridgeClient
    client = HueBridgeClient(username='sometestusername')

Note: The Hue API requires the username to be at least 10 characters long. Attempting to create a shorter username will result in an error like: ``Exception: invalid value,  tooshort, for parameter, username``.

Development
================
API Documentation for the Phillips Hue is here:

http://www.developers.meethue.com/

You can test the API of your phillips hue by going to ``/debug/clip.html``.

Running tests
=================
To run the tests you can do the following:

.. code-block:: bash

    tox -e py34

The first time you run the tests you will need to hold the link button.

Credits
==================
- SSDP Module originally developed by Dan Krause here:
  https://gist.github.com/dankrause/6000248

- Hex -> XY originally developed by Ben Knight here:
  https://github.com/benknight/hue-python-rgb-converter
