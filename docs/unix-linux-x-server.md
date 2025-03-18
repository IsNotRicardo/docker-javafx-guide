# Setting up an X server on Unix/Linux

> [!WARNING]
> This guide has not been tested and might be incomplete.

## X.org Xhost

Most Unix-based systems come with an X server installed by default in the form of [Xhost](https://www.ibm.com/docs/en/aix/7.1?topic=x-xhost-command).
All you need to do is to configure the X server to allow Docker containers to connect to it. You can do
this by running the following command:

```bash
xhost +local:docker
```

> [!IMPORTANT]
> This command disables access control for the X server, allowing Docker containers to connect to it.
> 
> You can revert this change by running the following command:
> ```bash
> xhost -local:docker
> ```

You have successfully configured your X server. You can now proceed to the [next step](docker-javafx-guide.md#building-and-running).