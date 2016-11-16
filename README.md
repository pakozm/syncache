SynCache
========

The aim of this package is to synchronize a (probably) remote folder
and a local folder, in such a way you can perform grid computing over
a cluster of computers and automatically synchronize their copy of
data. It is suitable for slow network connections, so the idea is to
copy the data from the network into local disks. By using a temporary
folder you can delete it when no needed or just restart the machine.
But if you need more than one execution with the same data, this
package ensures it is in sync with the remote resource.

Usage
-----

```Python
syn = SynCache("/home/user", "/tmp/dest")
syn.sync()
syn.getpath("sample.txt")
# '/tmp/dest/sample.txt'
syn.reverse_sync()
```

```Python
syn = SynCache("/home/user", gen_hashed_folder(sys.argv))
syn.getpath("sample.txt")
#'/tmp/syncache-6s7fWriA9vSwnMzXsFfSuw=='
```