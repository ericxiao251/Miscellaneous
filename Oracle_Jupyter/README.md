# Jupyter/IPython notebooks for Oracle RDBMS

Author: Luca.Canali@cern.ch, June 2016

**Blog entry:http://externaltable.blogspot.com/2016/06/ipythonjupyter-notebooks-for-oracle.html**

---
This folder contains example notebooks on how to use Jupyter/IPython for querying Oracle databases and integrating with Python data analysis and visualization tools.

**Example notebooks:**

| Notebook                   | Short description
| -------------------------- | -------------------------------------------------------------------------------------
| [**Oracle_IPython_sqlplus**](Oracle_IPython_sqlplus.ipynb) | Examples of how to use sqlplus inside Jupyter notebooks. It is based on the use of %%bash cell magic and here documents to wrap up sqlplus inside Jupyter cells.
| [**Oracle_IPython_cx_Oracle_pandas**](Oracle_IPython_cx_Oracle_pandas.ipynb) | Examples of how to query Oracle from Python using cx_Oracle and how to integrate with pandas and visualization with matplotlib.
| [**Oracle_IPython_SQL_magic**](Oracle_IPython_SQL_magic.ipynb) | Examples of how to query Oracle using %sql line magic (or %%sql cell magic) and the integration with cx_Oracle and pandas.

---
**Dependencies and pointers to build a test environment:**
- Install **IPython and Jupyter**. The following assumes [Anaconda](https://www.continuum.io/downloads) from Continuum Analytics)
- Install the **Oracle client**
    - Download the software from OTN: <http://www.oracle.com/technetwork/topics/linuxx86-64soft-092277.html>
    - On that same link you can find the installation instructions (scroll down by the end of the page)
    - Example of the actions: perform `ln -s libclntsh.so.12.1 libclntsh.so` (12c version) and `export LD_LIBRARY_PATH={oracle client home}`
    - I have tested this with Oracle client versions 12.1.0.2 and 11.2.0.4 on Linux
- Post client installation:
    - set environment: `export ORACLE_HOME={path to the Oracle client installation}`
    - If not already installed, install libaio (yum install libaio)
- Check that the Oracle client works and all dependencies are set by running sqlplus from the Oracle client home, example:
    - check client connectivity with: `sqlplus username/password@dbserver:port/service_name`
- Install **cx_Oracle**, for example with `pip install cx_Oracle`
- Install **ipython-sql**
   - download from <https://github.com/LucaCanali/ipython-sql>
   - `cd ipython-sql` and `(sudo) python setup.py install`
   - Optionally install the official version on PyPi using `pip install ipython-sql`

