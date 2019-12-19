# HelloDockerfile


## 1. Clone repo locally

```sh
git clone https://github.com/ecwpz91/HelloDockerfile.git
```

## 2. Change to directory

```sh
cd HelloDockerfile
```

## 3. Create a new project for you application

```sh
oc new-project hellodockerfile --display-name="Hello Dockerfile Demo"
```

## 4. Create a new build for your application

```sh
oc new-build --strategy docker --binary --docker-image centos:centos7 --name myapp
```

## 5. Start a binary build using the local directory’s content

```sh
oc start-build myapp --from-dir . --follow
```

## 6. Deploy the application using new-app, then create a route for it

```sh
oc new-app myapp
```

## 7. Expose route to application

```sh
oc expose svc/myapp
```

## 8. Get the host name for your route and navigate to it:

```sh
oc get route myapp
```

# References

https://docs.openshift.com/container-platform/3.11/dev_guide/dev_tutorials/binary_builds.html#binary-builds-private-code
