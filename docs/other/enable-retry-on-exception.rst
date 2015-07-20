Enable retry on exceptions
==========================

Retry decorator is general purpose library for adding retry mechanism.
This helps to handle retry on the known and user provided
exceptions.


Using retry decorator
---------------------

Retry mechanism is disabled by default, and can be enabled easily
by either setting module level variable ``RETRY_FAILED_HTTP_REQUESTS``
or by environment variable ``LIBCLOUD_RETRY_FAILED_HTTP_REQUESTS``.
Retry also allows you to customize on timeout, delay between attempts and
multiplier backoff added to delay between attempt. 

.. sourcecode:: python

    import libcloud.common.base
    from libcloud.utils.misc import retry

    libcloud.common.base.RETRY_FAILED_HTTP_REQUESTS = True
    hostname = '/'
    retry_request = retry(timeout=1, retry_delay=1, backoff=1)
    retry_request(self.connection.request)(action=hostname)


