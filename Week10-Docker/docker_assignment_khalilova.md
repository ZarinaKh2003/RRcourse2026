## Task 1.1
```
~/zar/hello-docker via 🐳 colima via 🐍 v3.12.11 
❯ docker build -t hello-docker .
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  3.072kB
Step 1/4 : FROM python:3.9-slim
3.9-slim: Pulling from library/python
c23f4b503473: Pulling fs layer
479b8ad8bcc3: Pulling fs layer
a16e55119267: Pulling fs layer
ebfe7d4fa0c5: Pulling fs layer
2c924589a7b3: Download complete
c23f4b503473: Download complete
94fc6135d9ca: Download complete
479b8ad8bcc3: Download complete
ebfe7d4fa0c5: Download complete
a16e55119267: Download complete
479b8ad8bcc3: Pull complete
a16e55119267: Pull complete
c23f4b503473: Pull complete
ebfe7d4fa0c5: Pull complete
Digest: sha256:2d97f6910b16bd338d3060f261f53f144965f755599aab1acda1e13cf1731b1b
Status: Downloaded newer image for python:3.9-slim
 ---> 2d97f6910b16
Step 2/4 : WORKDIR /app
 ---> Running in 46d26651f036
 ---> Removed intermediate container 46d26651f036
 ---> 0918ec8f4770
Step 3/4 : COPY hello.py .
 ---> 8076fe2bdcb6
Step 4/4 : CMD ["python", "hello.py"]
 ---> Running in 0e58c62be368
 ---> Removed intermediate container 0e58c62be368
 ---> a4d0368b4763
Successfully built a4d0368b4763
Successfully tagged hello-docker:latest

~/zar/hello-docker via 🐳 colima via 🐍 v3.12.11 
❯ docker run --rm hello-docker
Hello from Python 3.9 inside a container!

```

## Task 1.2
```
~/zar/hello-docker via 🐳 colima via 🐍 v3.12.11 
❯ docker build -t hello-docker .
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  3.072kB
Step 1/4 : FROM python:3.9-slim
 ---> 2d97f6910b16
Step 2/4 : WORKDIR /app
 ---> Using cache
 ---> 0918ec8f4770
Step 3/4 : COPY hello.py .
 ---> 704a09c50fc6
Step 4/4 : CMD ["python", "hello.py"]
 ---> Running in 4d698318d28f
 ---> Removed intermediate container 4d698318d28f
 ---> a68fffa80f10
Successfully built a68fffa80f10
Successfully tagged hello-docker:latest

~/zar/hello-docker via 🐳 colima via 🐍 v3.12.11 
❯ docker run --rm hello-docker
Traceback (most recent call last):
  File "/app/hello.py", line 1, in <module>
    import sys, pandas
ModuleNotFoundError: No module named 'pandas'
```
```
~/zar/hello-docker via 🐳 colima via 🐍 v3.12.11 
❯ docker build -t hello-docker .
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  3.072kB
Step 1/5 : FROM python:3.9-slim
 ---> 2d97f6910b16
Step 2/5 : WORKDIR /app
 ---> Using cache
 ---> 0918ec8f4770
Step 3/5 : COPY hello.py .
 ---> Using cache
 ---> 704a09c50fc6
Step 4/5 : RUN pip install pandas==2.3.3
 ---> Running in 9668ec9cfc9b
Collecting pandas==2.3.3
  Downloading pandas-2.3.3-cp39-cp39-manylinux_2_24_aarch64.manylinux_2_28_aarch64.whl (12.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12.2/12.2 MB 8.6 MB/s eta 0:00:00
Collecting numpy>=1.22.4
  Downloading numpy-2.0.2-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (13.9 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 13.9/13.9 MB 6.9 MB/s eta 0:00:00
Collecting python-dateutil>=2.8.2
  Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 229.9/229.9 kB 10.6 MB/s eta 0:00:00
Collecting tzdata>=2022.7
  Downloading tzdata-2026.2-py2.py3-none-any.whl (349 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 349.3/349.3 kB 10.5 MB/s eta 0:00:00
Collecting pytz>=2020.1
  Downloading pytz-2026.1.post1-py2.py3-none-any.whl (510 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 510.5/510.5 kB 10.4 MB/s eta 0:00:00
Collecting six>=1.5
  Downloading six-1.17.0-py2.py3-none-any.whl (11 kB)
Installing collected packages: pytz, tzdata, six, numpy, python-dateutil, pandas
Successfully installed numpy-2.0.2 pandas-2.3.3 python-dateutil-2.9.0.post0 pytz-2026.1.post1 six-1.17.0 tzdata-2026.2
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv

[notice] A new release of pip is available: 23.0.1 -> 26.0.1
[notice] To update, run: pip install --upgrade pip
 ---> Removed intermediate container 9668ec9cfc9b
 ---> f12eda4d3b90
Step 5/5 : CMD ["python", "hello.py"]
 ---> Running in 094ebedcfcfa
 ---> Removed intermediate container 094ebedcfcfa
 ---> a5cc9f19ad91
Successfully built a5cc9f19ad91
Successfully tagged hello-docker:latest

~/zar/hello-docker via 🐳 colima via 🐍 v3.12.11 
❯ docker run --rm hello-docker
Python 3.9, pandas 2.3.3
```


## Dockerfile
```
FROM python:3.9-slim
WORKDIR /app
COPY hello.py .
RUN pip install pandas==2.3.3
CMD ["python", "hello.py"]
```

## Task 2.1
If I don’t pin the version of Pandas and just write pip install pandas, the version that gets installed can change over time. It might work today but if someone tried to run the same docker file  later, they could get the newer version with different behavior or even breaking changes. For example, some functions might be removed or behave differently, and then the code stops working even though nothing was changed on our side.
Pinning the version makes sure that everyone runs exactly the same environment, so the results are consistent.

## Task 2.2
I think sending the built image (the “cake”) is better for reproducible research. Even if someone has docker file, rebuilding it later might give slightly different results because dependencies can change or external services might update.
With a built image, everything is already fixed - exact versions, environment and setup - so there is no rest of differences during installation. A concrete example id a package version gets removed or updated, rebuilding might fail or behave differently, but the existing image will still run the same.


