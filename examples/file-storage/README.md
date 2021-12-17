# File Storage

## Overview

This guide explains how to add and retrieve an image file to/from an FTP server using Ballerina.
The below are the detailed explanations of each of the steps of this example.

### Step 1 - Start the FTP Server

Execute the Gradle run command on the Java project of the sample FTP server. This would start the FTP server.

### Step 2 - Initialize the FTP Client with Credentials

In order to interact with an FTP server, an FTP Client has to be initialized with the server-related connection details
and your credentials. The Ballerina FTP client is configured to run on port `20210` of `localhost`.

### Step 3 - Put the Image File

A blocked stream of bytes of the local image file is created and passed to the FTP client along with the destination
path name.
Then, the image file is stored in the FTP server.

### Step 4 - Get the Stored Image File Using the Client

A stream of bytes of the image stored in the FTP server is retrieved.

### Step 5 - Write the Received Stream as a File

The received byte stream is written to the local machine, which would re-generate the received image file.

### Step 6 - Close the File Stream

When all the file-related operations are finished, the byte stream corresponding to the received image file is closed.


## Testing

You can run the above code in your local environment. Navigate to the
[`examples/file-storage/server`](./server)  directory, and start the FTP server by building and running the Gradle-based code
with the following command.
```shell
$ ./gradlew run
```

Then, navigate to the [`examples/file-storage/client`](./client) directory, and execute the command below.
```shell
$ bal run
```

The successful execution of the client should show the output below.
```shell
Compiling source
	ftp/file_storage:1.0.0

Running executable
```

Now, check the current directory for the received file. The `localDog.png` image file should be available.