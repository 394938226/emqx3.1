emqx-rel
========



Build on Linux/Unix/Mac
-----------------------


Build Docker Image
------------------

```

```

Build on Windows
----------------

Install Erlang/OTP-R21.0 and MSYS2-x86_64 for erlang.mk:

```
https://erlang.mk/guide/installation.html#_on_windows
```

Clone and build the EMQ X Broker with erlang.mk:

```
git clone https://github.com/emqx/emqx-rel.git emqx-rel
cd emqx-rel
make
cd _rel\emqx
bin\emqx console
```

License
-------

Apache License Version 2.0

Author
------

EMQ X Team.
