This source for this project can be found on GitLab at https://gitlab.com/joelostblom/session_info.

`session_info` can be used from a script like so:

```python
import math

import natsort
import pandas
import session_info


session_info.show()
```


Output:

```
Session information:
-----
natsort             7.1.1
pandas              1.2.2
session_info        1.0.0
-----
IPython             7.23.0
jupyter_client      6.1.12
jupyter_core        4.7.1
-----
Python 3.9.2 | packaged by conda-forge | (default, Feb 21 2021, 05:02:46) [GCC 9.3.0]
Linux-5.11.13-arch1-1-x86_64-with-glibc2.33
-----
Session information updated at 2021-05-06 09:59
```

The default behavior is to only output modules not in the standard library,
which is why the `math` module is omitted above (it can be included by
specifying `std_lib=True`). To include not only the explicitly imported
modules, but also any dependencies they import internally, specify `dependencies=True`.

When `session_info` is invoked from a Jupyter Notebook,
the output is concealed in `<details>` tags
and will only show when clicked.
Since this saves visual real estate,
any modules imported indirectly as dependencies
will be included by default
and it looks like this:

<details>
<summary>Click to view session information</summary>
<pre>
-----
natsort             7.1.1
pandas              1.2.2
session_info        1.0.0
-----
</pre>
<details>
<summary>Click to view modules imported as dependencies</summary>
<pre>
backcall            0.2.0
cython_runtime      NA
dateutil            2.8.1
decorator           5.0.7
ipykernel           5.5.3
ipython_genutils    0.2.0
jedi                0.18.0
numpy               1.20.2
parso               0.8.2
pexpect             4.8.0
pickleshare         0.7.5
prompt_toolkit      3.0.18
ptyprocess          0.7.0
pygments            2.8.1
pytz                2021.1
six                 1.15.0
storemagic          NA
tornado             6.1
traitlets           5.0.5
wcwidth             0.2.5
zmq                 22.0.3
</pre>
</details>
<pre>
-----
IPython             7.23.0
jupyter_client      6.1.12
jupyter_core        4.7.1
-----
Python 3.9.2 | packaged by conda-forge | (default, Feb 21 2021, 05:02:46) [GCC 9.3.0]
Linux-5.11.13-arch1-1-x86_64-with-glibc2.33
-----
Session information updated at 2021-05-06 09:59
</pre>
</details>
