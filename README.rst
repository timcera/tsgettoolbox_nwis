.. image:: https://img.shields.io/coveralls/github/timcera/tsgettoolbox_nwis
    :alt: Test Coverage
    :target: https://coveralls.io/r/timcera/tsgettoolbox_nwis?branch=master
    :height: 20

.. image:: https://img.shields.io/pypi/v/tsgettoolbox_nwis
    :alt: Latest release
    :target: https://pypi.python.org/pypi/tsgettoolbox_nwis/
    :height: 20

.. image:: https://img.shields.io/pypi/l/tsgettoolbox_nwis
    :alt: BSD-3 clause license
    :target: https://pypi.python.org/pypi/tsgettoolbox_nwis/
    :height: 20

.. image:: https://img.shields.io/pypi/pyversions/tsgettoolbox_nwis
    :alt: PyPI - Python Version
    :target: https://pypi.org/project/tsgettoolbox_nwis/
    :height: 20

tsgettoolbox_nwis - Quick Guide
===============================
DEPRECATED: Replaced by the functions in the 'tsgettoolbox_wdfn' plugin.

USGS will remove the NWIS web service that 'tsgettoolbox_nwis' uses between
11-2026 and 02-2027.  The 'tsgettoolbox_nwis' plugin will be removed from the
tsgettoolbox package at that time.  Users should transition to the
'tsgettoolbox_wdfn' functions.

The 'tsgettoolbox_nwis' is a plugin-in for 'tsgettoolbox' that supplies
a command line interface and Python library to get time-series data from the
USGS National Water Information System (WSIS).  The tsgettoolbox_nwis will work
with Python 3.10+.

Documentation
-------------
Reference documentation is at `tsgettoolbox_documentation`_.

Installation
------------
At the command line::

    $ pip install tsgettoolbox_nwis

Usage Summary - Command Line
----------------------------
Just run 'tsgettoolbox --help' to get a list of subcommands.  To get detailed
help for a particular sub-command, for instance 'nwis', type 'tsgettoolbox
nwis --help'.

+----------------------------------+---------+--------+---------+----------+-----------------------+
| Sub-command                      | Spatial | Time   | Type    | Time     | Description           |
|                                  | Extent  | Extent |         | Interval |                       |
+==================================+=========+========+=========+==========+=======================+
| tsgettoolbox_nwis DEPRECATED use | US      | varies | station | varies   | USGS National Water   |
| wdfn_* functions from            |         |        |         |          |                       |
| tsgetoolbox_wdfn instead.        |         |        |         |          |                       |
+----------------------------------+---------+--------+---------+----------+-----------------------+
| nwis_iv DEPRECATED: use          | US      | varies | station | E        | USGS NWIS             |
| tsgettoolbox_wdfn.               |         |        |         |          | Instantaneous Values  |
| wdfn_continuous                  |         |        |         |          |                       |
+----------------------------------+---------+--------+---------+----------+-----------------------+
| nwis_dv DEPRECATED: use          | US      | varies | station | D        | USGS NWIS Daily       |
| tsgettoolbox_wdfn.wdfn_daily     |         |        |         |          | Values                |
+----------------------------------+---------+--------+---------+----------+-----------------------+
| nwis_site DEPRECATED: use        | US      | varies | station | -NA-     | USGS NWIS Site        |
| tsgettoolbox_wdfn.               |         |        |         |          | Database              |
| wdfn_monitoring_locations        |         |        |         |          |                       |
+----------------------------------+---------+--------+---------+----------+-----------------------+
| nwis_gwlevels DEPRECATED: use    | US      | varies | station | varies   | USGS NWIS Groundwater |
| tsgettoolbox_wdfn.               |         |        |         |          |                       |
| wdfn_field_measurements          |         |        |         |          |                       |
+----------------------------------+---------+--------+---------+----------+-----------------------+
| nwis_measurements DEPRECATED:    | US      | varies | station | varies   | USGS NWIS             |
| use tsgettoolbox_wdfn.           |         |        |         |          | Measurements          |
| wdfn_field_measurements          |         |        |         |          |                       |
+----------------------------------+---------+--------+---------+----------+-----------------------+
| nwis_peak DEPRECATED: use        | US      | varies | station | varies   | USGS NWIS Peak        |
| tsgettoolbox_wdfn.wdfn_peaks     |         |        |         |          |                       |
+----------------------------------+---------+--------+---------+----------+-----------------------+
| nwis_stat DEPRECATED: use        | US      | varies | station | varies   | USGS NWIS Statistic   |
| tsgettoolbox_wdfn.               |         |        |         |          |                       |
| wdfn_read_normal_observations or |         |        |         |          |                       |
| tsgettoolbox_wdfn.               |         |        |         |          |                       |
| wdfn_read_interval_observations  |         |        |         |          |                       |
+----------------------------------+---------+--------+---------+----------+-----------------------+

+-------------------+-------------+
| Time Interval     | Description |
| Code              |             |
+===================+=============+
| E                 | Event       |
+-------------------+-------------+
| D                 | Daily       |
+-------------------+-------------+

Usage Summary - Python Library
------------------------------
To use the tsgettoolbox in a project::

    from tsgettoolbox import tsgettoolbox
    df = tsgettoolbox.nwis_dv(sites="02325000", startDT="2015-07-01", endDT="2015-07-30")
    print(df.head())

Refer to the API Documentation at `tsgettoolbox_api`_.

Usage Summary - Command Line
----------------------------

    tsgettoolbox nwis_dv \
        --sites 02325000 \
        --startDT 2015-07-01 \
        --endDT 2015-07-30 > output.csv

Refer to the command line documentation at `tsgettoolbox_cli`_.

Development
~~~~~~~~~~~
Development is managed on bitbucket or github.
https://bitbucket.org/timcera/tsgettoolbox_nwis/overview.
https://github.com/timcera/tsgettoolbox_nwis

.. _tsgettoolbox_documentation: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/index.html
.. _tsgettoolbox_api: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/function_summary.html
.. _tsgettoolbox_cli: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/command_line.html
