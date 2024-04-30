# Nest JS Microservices - Demo Products App

![NestJS](https://cdn.dribbble.com/users/808903/screenshots/3831862/dribbble_szablon__1_1.png?resize=400x300&vertical=center)

## Description
Project based on a tutorial that makes use of NestJS to create a microservices architecture. The project is divided into different microservices (auth, products, paymemnts, orders), each with its own database and communication between them is done through NATS. The project also includes a RESTFUL Client Gateway that is responsible for client requests and communication with the microservices.

## Tech Stack
- Typescript
- Node JS
- Nest JS
- Prisma ORM
- DB: Postgres | SQLite | MongoDB
- Docker and Docker Compose
- NATS as a Broker
- Stripe
- JWT Auth
- Joi to validate .env files
- Git Submodules

## Dev
1. Clone repo
2. Create `.env` file based on `.env.template`
3. Run command `git submodule update --init --recursive` to rebuild all microservices
4. Ejecutar el comando `docker compose up --build`

### Steps to recreate Git Submodules
1. Create a new repository in GitHub
2. Clone the repository in the local machine
3. Add the submodule, where `repository_url` is the url of the repository and `directory_name` is the name of the folder where you want the submodule to be saved (it should not exist in the project)
```
git submodule add <repository_url> <directory_name>
```
4. Add the changes to the repository (git add, git commit, git push)
```
git add .
git commit -m "Add submodule"
git push
```
5. When someone clones the repository for the first time, they must run the following command to initialize and update the submodules
```
git submodule update --init --recursive
```
6. To update the references of the submodules
```
git submodule update --remote
```

## Important
If you are working in a repository that has the submodules, **first update and push** in the submodule and **then** in the main repository.

Otherwise, the references of the submodules in the main repository will be lost and you will have to resolve conflicts.


# Prod

1. Clone repo
2. Create `.env` file based on `.env.template`
3. Run command
```
docker compose -f docker-compose.prod.yml build
```