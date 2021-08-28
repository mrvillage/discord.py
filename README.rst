discord.py2
==========

A modern, easy to use, feature-rich, and async ready API wrapper for Discord written in Python.

The Future of discord.py
--------------------------

Danny has archived the project, I'm going to try my very best to keep an up to date version but we'll see how that goes. Huge thanks to Danny for what he's done on the library, hopefully I can live up to even a small fraction of what he did.

Please read the `gist <https://gist.github.com/Rapptz/4a2f62751b9600a31a0d3c78100287f1>`_ for the future of this project. It's been a good one.

Key Features
-------------

- Modern Pythonic API using ``async`` and ``await``.
- Proper rate limit handling.
- Optimised in both speed and memory.

Installing
----------

**Python 3.8 or higher is required**

To install the library without full voice support, you can just run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U discord.py2

    # Windows
    py -3 -m pip install -U discord.py2

Otherwise to get voice support you should run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U "discord.py2[voice]"

    # Windows
    py -3 -m pip install -U discord.py2[voice]


To install the development version, do the following:

.. code:: sh

    $ git clone https://github.com/mrvillage/discord.py2
    $ cd discord.py2
    $ python3 -m pip install -U .[voice]


Optional Packages
~~~~~~~~~~~~~~~~~~

* `PyNaCl <https://pypi.org/project/PyNaCl/>`__ (for voice support)

Please note that on Linux installing voice you must install the following packages via your favourite package manager (e.g. ``apt``, ``dnf``, etc) before running the above commands:

* libffi-dev (or ``libffi-devel`` on some systems)
* python-dev (e.g. ``python3.6-dev`` for Python 3.6)

Quick Example
--------------

.. code:: py

    import discord

    class MyClient(discord.Client):
        async def on_ready(self):
            print('Logged on as', self.user)

        async def on_message(self, message):
            # don't respond to ourselves
            if message.author == self.user:
                return

            if message.content == 'ping':
                await message.channel.send('pong')

    client = MyClient()
    client.run('token')

Bot Example
~~~~~~~~~~~~~

.. code:: py

    import discord
    from discord.ext import commands

    bot = commands.Bot(command_prefix='>')

    @bot.command()
    async def ping(ctx):
        await ctx.send('pong')

    bot.run('token')

You can find more examples in the examples directory.

Links
------

- `Documentation <https://discordpy2.readthedocs.io/en/latest/index.html>`_
