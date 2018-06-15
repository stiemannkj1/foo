 # Steps to reproduce:

1. Clone the project and enter its directory:

        git clone https://github.com/stiemannkj1/foo.git && cd foo

2. Release `1.0.0` (locally):

        git checkout 1.0.0 && mvn clean install

3. Release `2.0.0` (locally):

        git checkout 2.0.0 && mvn clean install

4. Release `1.1.0` (locally):

        git checkout 1.1.0 && mvn clean install

5. Try to build `2.0.0` again:

        git checkout 2.0.0 && mvn clean install

If the problem still exists, the build will fail with the following error:

```
[INFO] The baseline version was found to be 1.1.0
[ERROR] Baseline mismatch for package com.liferay.faces.foo, MAJOR change. Current is 1.0.1, repo is 1.1.0, suggest 2.0.0 or -
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 1.592 s
[INFO] Finished at: 2018-06-15T15:01:02-04:00
[INFO] ------------------------------------------------------------------------
```

If the problem is fixed, the build will succeed.