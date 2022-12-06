Usage
=====

.. _setup:

Setup
------------
Python 3.9, we recommand running BLINK in a venv 
pipenv::
   $ pipenv install --python 3.9
   $ pipenv shell

mongodb(optional)::
   $ cp db_config.py.example db_config.py
   $ vim db_config.py
   
   - specify ***db_config.py*** for your db connection

Entry point
----------------

`blink.cli`

**Example usage:**

`python -m blink.cli -i sample.apk -o csv -o txt -s -t -db -T test`

- output csv, txt and show to console
- time the analysis critical steps
- store result in database
- assign a tag to mark this analysis run

.. code-block:: console
Usage: python -m blink.cli [OPTIONS]

  Blink: Andoird binary lint kit

Options:
  -i, --input PATH                input APK File/ Folder(single layer)
                                  [required]
  -d, --outdir DIRECTORY          Analysis Report Output Directory
  -o, --output-type [txt|xml]
                                  Output file type
  -r, --rules DIRECTORY           Rules folder need to be checked
  -s, --show                      Show result to console
  -v, --verbose                   Show detailed result(imply show)
  -db, --database              Store result to database(need to set db_config)
  -T, --analyze-tag TEXT       Analysis tag mark this round of analysis(also
                               used as output dirname)
  -t, --timed                  Time critical steps
  -p, --prediction             Riskware Predicton(CICMalDroid2020)
  -seq, --sequential           Analyze target sequentially (disable
                               multiprocessing)
  --timeout INTEGER            Timeout value (in sec)
  -n, --process-cnt INTEGER    Mutiprocess core count
  --version
  --help                       Show this message and exit.
```