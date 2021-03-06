Date parsing and normalization utilities based on FlexiDate.

To parse dates use parse, e.g.::

    from flexidate import parse
    parse('1890') -> FlexiDate(year=u'1890')
    parse('1890?') -> FlexiDate(year=u'1890', qualifier='Uncertainty: 1890?')

Once you have a FlexiDate you can get access to attributes (strings of course
...)::

    from flexidate import parse
    fd = parse('Jan 1890')
    fd.year # u'1890'
    fd.month # u'01'

Note how all fields are retained as strings -- this is the only way to not lose
information.

However, it's easy to convert to other forms::

    fd.as_float() # 1890
    fd.as_datetime() # datetime(1890,01,01)


Background
==========

FlexiDate is focused on supporting:

  1. Dates outside of Python (or DB) supported period (esp. dates < 0 AD)
  2. Imprecise dates (c.1860, 18??, fl. 1534, etc)
  3. Normalization of dates to machine processable versions
  4. Sortable in the database (in correct date order)

Flexidate builds on the excellent dateutil though it can be used without it.

For more information see: http://www.rufuspollock.org/2009/06/18/flexible-dates-in-python/


Developers
==========

Tests can be found in test_flexidate.py.

Patches are welcome - please include additional tests where relevant.

