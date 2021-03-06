Supported Browsers
##################

.. note::

    A Browser is considered supported if it is tested in continuous integration.
    Other browsers and browser versions might also work, but are not tested.


.. list-table:: Browsers
   :header-rows: 1

   * - Browser Name
     - Supported Versions
     - Supported Service
     - OS
   * - Firefox
     - 59
     - Geckodriver 0.20.0
     - Linux, macOS, Windows 10
   * - PhantomJS
     - 1.9.8
     - PhantomJS 1.9.8
     - Linux, macOS, Windows 10
   * - Google Chrome
     - 65
     - Chromedriver 2.37
     - Linux, macOS, Windows 10
   * - Internet Explorer
     - 11 (See :ref:`ie11`)
     - IEDriverServer
     - Windows 10

Remote sessions are available via the :py:class:`arsenic.services.Remote` but not all APIs may be available.


Headless Google Chrome
**********************


To use Google Chrome headless, use::

    service = services.Chromedriver()
    browser = browsers.Chrome(chromeOptions={
        'args': ['--headless', '--disable-gpu']
    })
    async with get_session(service, browser) as session:
        ...


Headless Firefox
****************

To use Firefox headless, use::

    service = services.Geckodriver()
    browser = browsers.Firefox(firefoxOptions={
        'args': ['-headless']
    })
    async with get_session(service, browser) as session:
        ...
