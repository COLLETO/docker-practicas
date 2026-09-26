Practica #2 Luis Fernandez Miranda 

➜  ~ git:(main) ✗ cd ..
➜  /home pwd
/home
➜  /home ls
node  student
➜  /home cd student 
➜  ~ git:(main) ✗ ls
ai-ops  dockerlabs     index.html         kubelabs    ops               snap
dev     get-docker.sh  kind-cluster.yaml  labs-luisf  skills-lock.json
➜  ~ git:(main) ✗ cd labs-luisf
➜  labs-luisf git:(main) ✗ mkdir Practica#2
➜  labs-luisf git:(main) ✗ cd Practica\#2 
➜  Practica#2 git:(main) ✗ cd ..
➜  labs-luisf git:(main) ✗ mkdir Practica#1
➜  labs-luisf git:(main) ✗ ls
Practica#1  Practica#2
➜  labs-luisf git:(main) ✗ cd Practica\#2
➜  Practica#2 git:(main) ✗ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
➜  Practica#2 git:(main) ✗ git clone https://github.com/docker/getting-started.git

Cloning into 'getting-started'...
remote: Enumerating objects: 998, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 998 (delta 3), reused 1 (delta 1), pack-reused 993 (from 2)
Receiving objects: 100% (998/998), 5.23 MiB | 16.64 MiB/s, done.
Resolving deltas: 100% (536/536), done.
➜  Practica#2 git:(main) ✗ ls
getting-started
➜  Practica#2 git:(main) ✗ cd getting-started/app

➜  app git:(master) Dockerfile

zsh: command not found: Dockerfile
➜  app git:(master) nano Dockerfile

➜  app git:(master) cat Dockerfile
cat: Dockerfile: No such file or directory
➜  app git:(master) nano Dockerfile

➜  app git:(master) cat Dockerfile 
cat: Dockerfile: No such file or directory
➜  app git:(master) nano Dockerfile

➜  app git:(master) cat Dockerfile 
FROM node:18-alpine

RUN apk add --no-cache python3 g++ make

WORKDIR /app

COPY . .

RUN yarn install --production

CMD ["node", "src/index.js"]
➜  app git:(master) docker build -t todo-app .

[+] Building 32.5s (11/11) FINISHED                                     docker:default
 => [internal] load build definition from Dockerfile                              0.0s
 => => transferring dockerfile: 185B                                              0.0s
 => [internal] load metadata for docker.io/library/node:18-alpine                 0.8s
 => [auth] library/node:pull token for registry-1.docker.io                       0.0s
 => [internal] load .dockerignore                                                 0.0s
 => => transferring context: 2B                                                   0.0s
 => [internal] load build context                                                 0.1s
 => => transferring context: 4.59MB                                               0.1s
 => [1/5] FROM docker.io/library/node:18-alpine@sha256:8d6421d663b4c28fd3ebc4983  2.3s
 => => resolve docker.io/library/node:18-alpine@sha256:8d6421d663b4c28fd3ebc4983  0.0s
 => => sha256:25ff2da83641908f65c3a74d80409d6b1b62ccfaab220b9ea70b80 446B / 446B  0.1s
 => => sha256:dd71dde834b5c203d162902e6b8994cb2309ae049a0eabc4 40.01MB / 40.01MB  0.9s
 => => sha256:f18232174bc91741fdf3da96d85011092101a032a93a388b79 3.64MB / 3.64MB  0.5s
 => => sha256:1e5a4c89cee5c0826c540ab06d4b6b491c96eda01837f430bd 1.26MB / 1.26MB  0.4s
 => => extracting sha256:f18232174bc91741fdf3da96d85011092101a032a93a388b79e99e6  0.1s
 => => extracting sha256:dd71dde834b5c203d162902e6b8994cb2309ae049a0eabc4efea161  1.2s
 => => extracting sha256:1e5a4c89cee5c0826c540ab06d4b6b491c96eda01837f430bd47f0d  0.0s
 => => extracting sha256:25ff2da83641908f65c3a74d80409d6b1b62ccfaab220b9ea70b80d  0.0s
 => [2/5] RUN apk add --no-cache python3 g++ make                                 3.8s
 => [3/5] WORKDIR /app                                                            0.1s 
 => [4/5] COPY . .                                                                0.1s 
 => [5/5] RUN yarn install --production                                           6.4s 
 => exporting to image                                                           18.9s 
 => => exporting layers                                                          14.1s 
 => => exporting manifest sha256:cb9b54ca737d28ab1bf96023824b4041c3148c8d7a686cd  0.0s 
 => => exporting config sha256:3d4b8b889936569d6662c35b10468379977a4cae864d587ed  0.0s 
 => => exporting attestation manifest sha256:419b7b1682bc1051b4c644add2e47d0a8a8  0.0s 
 => => exporting manifest list sha256:a2b8b0101085ea479b98cc0fc8a8f7c298485c422f  0.0s 
 => => naming to docker.io/library/todo-app:latest                                0.0s
 => => unpacking to docker.io/library/todo-app:latest                             4.8s
➜  app git:(master) docker images

                                                                   i Info →   U  In Use
IMAGE                                  ID             DISK USAGE   CONTENT SIZE   EXTRA
cachac/dockerlabs_base:node14          ec19f34f2682       2.58GB          578MB        
colleadmin/dockerlabs:v1.0             1ef286d7e623        102MB         28.7MB        
demowebsite:1.0                        230811856b3d        250MB         66.3MB        
demowebsite:2.0                        97973c50f41e        250MB         66.3MB        
dockerlabs:latest                      1ef286d7e623        102MB         28.7MB        
kindest/node@sha256:3966ac761ae0136263ffdb6cfd4db23ef8a83cba8a463690e98317add2c9ba72
                                       3966ac761ae0       1.38GB          428MB        
ksteve17/kubelabs_publicapi:1.0.0      aeb34b1de561        252MB         48.2MB        
loadbalancer:latest                    213a1679af53        101MB         28.6MB        
nginx:stable-alpine                    985220252f38       93.6MB           27MB        
redis:alpine                           becdda6c7f4b        160MB         39.5MB        
todo-app:latest                        a2b8b0101085        723MB          184MB        
ubuntu:latest                          2260313b31c8        160MB         45.3MB        
wbitt/network-multitool:latest         db2810fe2c8d        433MB         96.7MB        
➜  app git:(master) docker run -d -p 8080:3000 --name todo-container todo-app

05ec07588dfe1ac5554a0a157ac950e6d8b690d6d8ef03a02f89e1af4cd3c4b5
➜  app git:(master) docker ps
CONTAINER ID   IMAGE      COMMAND                  CREATED          STATUS          PORTS                                         NAMES
05ec07588dfe   todo-app   "docker-entrypoint.s…"   16 seconds ago   Up 15 seconds   0.0.0.0:8080->3000/tcp, [::]:8080->3000/tcp   todo-container
➜  app git:(master) docker logs todo-container

Using sqlite database at /etc/todos/todo.db
Listening on port 3000
➜  app git:(master) curl http://localhost:8080


<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no, maximum-scale=1.0, user-scalable=0" />
    <link rel="stylesheet" href="css/bootstrap.min.css" crossorigin="anonymous" />
    <link rel="stylesheet" href="css/font-awesome/all.min.css" crossorigin="anonymous" />
    <link href="https://fonts.googleapis.com/css?family=Lato&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="css/styles.css" />
    <title>Todo App</title>
</head>
<body>
    <div id="root"></div>
    <script src="js/react.production.min.js"></script>
    <script src="js/react-dom.production.min.js"></script>
    <script src="js/react-bootstrap.js"></script>
    <script src="js/babel.min.js"></script>
    <script type="text/babel" src="js/app.js"></script>
</body>
</html>
➜  app git:(master) curl http://207.231.108.76:8080


<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no, maximum-scale=1.0, user-scalable=0" />
    <link rel="stylesheet" href="css/bootstrap.min.css" crossorigin="anonymous" />
    <link rel="stylesheet" href="css/font-awesome/all.min.css" crossorigin="anonymous" />
    <link href="https://fonts.googleapis.com/css?family=Lato&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="css/styles.css" />
    <title>Todo App</title>
</head>
<body>
    <div id="root"></div>
    <script src="js/react.production.min.js"></script>
    <script src="js/react-dom.production.min.js"></script>
    <script src="js/react-bootstrap.js"></script>
    <script src="js/babel.min.js"></script>
    <script type="text/babel" src="js/app.js"></script>
</body>
</html>
➜  app git:(master) docker rm -f todo-container

todo-container
➜  app git:(master) docker volume create todo-db

todo-db
➜  app git:(master) docker volume ls
DRIVER    VOLUME NAME
local     6ca37f6ef8c629f8cc629869b138b5d0433308da05c067c4b5ff83e0fcba77b4
local     93d20b4517a1ca9bbdb72980aaae5fc8392c1d9ff04e6207179e431e7016ef9a
local     21627146c1ecd8a54e9173ebbcd9b912557f41958071bf3b9fcb2be7872711a9
local     c0789d2910514b400bf1b5ab73f559eb35ff8bd6ebe70d6f47e865ffc91b70ac
local     data
local     todo-db
➜  app git:(master) 
➜  app git:(master) docker rm -f todo-container

➜  app git:(master) docker run -d -p 8080:3000 --name todo-container -v todo-db:/etc/todos todo-app

37f3b65197e97e1140f8b3ac94c50dba10e923eddb2ad90aaf036f6922fde404
➜  app git:(master) docker ps

CONTAINER ID   IMAGE      COMMAND                  CREATED          STATUS          PORTS                                         NAMES
37f3b65197e9   todo-app   "docker-entrypoint.s…"   50 seconds ago   Up 49 seconds   0.0.0.0:8080->3000/tcp, [::]:8080->3000/tcp   todo-container
➜  app git:(master) docker rm -f todo-container

todo-container
➜  app git:(master) docker run -d -p 8080:3000 --name todo-container -v todo-db:/etc/todos todo-app

3a2caf839c8fb940a896b86929399e339ee0ef7884d94bab10302dc00427f34d
➜  app git:(master) 

