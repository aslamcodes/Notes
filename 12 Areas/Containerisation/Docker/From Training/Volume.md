> Mapping the directory from physical path of the host machine to the container, so that whatever updates in both, ie physical and virtual, the changes will be reflected

```shell
docker run container -v ppath:vpath
```

> [!DANGER] This is for **development only** and not to use when production

```shell
docker run container -v ppath:vpath exclude_path
```

