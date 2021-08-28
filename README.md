# SWC Temas boilerplate

    SWC Teams Frontend Repo

## Structure

Here is the basic suggested skeleton for your app repo that each of the starter templates conforms to:

```bash
├── public(html file)
├── src
    ├──components(add your components here)
│   ├── layouts(add yours layout here)
│   └── pages(add yours pages here)
    └── routes(add all yours routes here)
├── README.md
├── node_modules
├── Dockerfile
├── docker_compose.yaml
├── package.json
├── yarn.lock(if using yarn)
└── .gitignore
```

> If you are using multer to save files on disc,configure it to save files inside pulblic>upload folder

## Dev Setup

> NOTE : Dockerfiles for react are mostly build in regards of production builds, in dev you don't need to use docker if you want coz react itlsef uses a lot of compoute resourdces

```bash
  #To start the containers
  docker-compose up
  #Stop containers in diff terminal than docker
  docker-compose --volumes down
  #build docker images
  docker-compose up --build #if there are changes in installed deps
  #faster builds
  COMPOSE_DOCKER_CLI_BUILD=1 DOCKER_BUILDKIT=1 docker-compose build
  #windows
  set "COMPOSE_DOCKER_CLI_BUILD=1" & set "DOCKER_BUILDKIT=1" & docker-compose build
  # or to make this permanent add following to docker daemon /etc/docker/daemon.json
  { "features": { "buildkit": true } }
```

**Withour docker**

```bash
yarn add/npm install
yarn start #start the server
#remove landing page designs if you want
```

**Helpers:**

1. Remove dangling images: `docker rmi $(docker images -f dangling=true -q ) -f`
2. Remove all volumes: `docker volume rm $(docker volume ls -q)`

