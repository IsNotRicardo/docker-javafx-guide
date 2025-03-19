# Setting up an X server on macOS

In this guide, we will use XQuatz, which you can install locally and that helps you run a GUI application through docker:

## XQuatz Installation

Run the following command to install XQuatz:
```sh
   brew install --cask xquartz
   ```
   This command will ask you for permission to run the XQuatz installation script. Type `Y` and press `Enter` to proceed.

   > [!NOTE]
   his command comes from XQuatz's [installation guide](https://www.xquartz.org/). Please refer to it for more information.

### XQuartz Configuration

**Set up XQuartz:**
```sh
   open -a XQuartz
```

<img src="images/macOS/open_XQuatz.png" alt="Open XQuatz" width="50%"/>

**Allow XQuartz to accept connections:**

Go to the Security tab and check "Allow connections from network clients".

<img src="images/macOS/allow_connections.png" alt="Allow connections" width="50%"/>

**Set the DISPLAY environment variable:**

```sh
    export DISPLAY=:0
```

**Allow connections to the X server:**

```sh
   xhost +localhost
```
It should display the following message:

```sh
localhost being added to access control list
```
<img src="images/macOS/local_host.png" alt="Add localhost to connections" width="50%"/>


You have successfully configured XQuartz to run the X server. You can now proceed to the [next step](docker-javafx-guide.md#building-and-running).