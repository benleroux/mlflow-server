# mlflow-server

This docker file will get the lastest ubuntu image, install all the pre-requisites and run the mlflow server

## Building the Docker image

```Bash
docker build .
```

> Make sure you're executing the above command within the same directory as the dockerfile

When completed, look for the image id (in bold)

>Step 11/11 : CMD ["mlflow", "server", "--default-artifact-root", "wasbs://mlflow@benleroux.blob.core.windows.net/", "--host", "0.0.0.0"]
> ---> Running in *4cd4d56654d9*
>Removing intermediate container *4cd4d56654d9*
> ---> *c928e2fdf147*
>Successfully built ***c928e2fdf147***
>SECURITY WARNING: You are building a Docker image from Windows against a non-Windows Docker host. All files and directories added to build context will have '-rwxr-xr-x' permissions. It is
recommended to double check and reset permissions for sensitive files and *directories*.

## Running the Docker image

```Bash
docker run --name mlflow -h mlflow -i -t -p 5000:5000 --rm ***c928e2fdf147***
```

The following options were used:

>--name to give a name to the container
>-h to name the container host
>-p 5000:5000 to open the port 5000 and map to port 5000 as the mlflow server runs under port 5000

Hope this helps!
