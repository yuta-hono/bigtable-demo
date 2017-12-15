# BigTable Demonstrate Timestamp with full scan
This demonstrate how Cloud BigTable can store the data into a table.

## SetUp

```
pip install -r requirements.txt
```

## Usage
```
usage: scan_all.py [-h] [--table TABLE] [--mode MODE] project_id instance_id

positional arguments:
  project_id     Your Cloud Platform project ID.
  instance_id    ID of the Cloud Bigtable instance to connect to.

optional arguments:
  -h, --help     show this help message and exit
  --table TABLE  Table to create and destroy. (default: Hello-Bigtable)
  --mode MODE    demo: (Default) Create and write to the table, then show the
                 data delete: Delete the table (default: demo)
```

### demo mode - Expected results
```
python scan_all.py yutah-catchup yutah-tokyo
Checking the bigtable-fullscan-demo table exists.
Writing some greetings to the table.
Getting a single greeting by row key.
	greeting0: Hello World! 23bf7332-7c1f-4247-bd9f-2a4ac48eedb8	@2017-12-15 02:49:20.461000+00:00
Scanning for all greetings:
	greeting2: Hello Python! 23bf7332-7c1f-4247-bd9f-2a4ac48eedb8	@2017-12-15 02:49:21.112000+00:00
	greeting2: Hello Python! 06987e5f-9885-4c62-9fe1-3d9fecffd454	@2017-12-15 02:49:16.205000+00:00
	greeting0: Hello World! 23bf7332-7c1f-4247-bd9f-2a4ac48eedb8	@2017-12-15 02:49:20.461000+00:00
	greeting0: Hello World! 06987e5f-9885-4c62-9fe1-3d9fecffd454	@2017-12-15 02:49:15.459000+00:00
	greeting1: Hello Cloud Bigtable! 23bf7332-7c1f-4247-bd9f-2a4ac48eedb8	@2017-12-15 02:49:21.039000+00:00
	greeting1: Hello Cloud Bigtable! 06987e5f-9885-4c62-9fe1-3d9fecffd454	@2017-12-15 02:49:16.128000+00:00
```