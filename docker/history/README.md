# how to check docker image layer history

get history of a docker image

```bash
docker history --no-trunc <image-name>
```

example:

```bash
IMAGE          CREATED        CREATED BY                                      SIZE      COMMENT
sha256:182...  2 days ago     RUN /bin/sh -c yum install -y jq ...            120MB     
<missing>      2 days ago     /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B        
<missing>      2 days ago     /bin/sh -c COPY file:... in /app/               25MB      
```
