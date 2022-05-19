# prisma-postgresql-seeding-example

# 🚀 Javascript full-stack 🚀

https://github.com/coding-to-music/prisma-postgresql-seeding-example

By Jordan McRae https://github.com/jordan-mcrae

https://stackfive.io/blog/seeding-relational-data-with-prisma

https://github.com/jordan-mcrae/prisma-postgresql-seeding-example

## Environment Values

```java
DATABASE_URL="postgres://username:password@localhost:5432/prisma-relational-example"
```

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/prisma-postgresql-seeding-example.git
git push -u origin main
```

## Install Postgresql on Debian and Ubuntu

You can either choose to use the version of PostgreSQL available in your distribution's default repositories or use repositories provided by the PostgreSQL project. Packages in the default repository are tested to work with all other software provided for your distribution, but may be older. Packages from the PostgreSQL project will be more up-to-date but may require extra configuration.

[Install using Debian or Ubuntu's default repositories](https://www.prisma.io/dataguide/postgresql/setting-up-a-local-postgresql-database#install-using-debian-or-ubuntus-default-repositories)

[Install using the PostgreSQL project's Debian and Ubuntu repositories](https://www.prisma.io/dataguide/postgresql/setting-up-a-local-postgresql-database#install-using-the-postgresql-projects-debian-and-ubuntu-repositories)

## Install using Debian or Ubuntu's default repositories

Both Ubuntu and Debian provide versions of PostgreSQL server as packages within their default repositories. The PostgreSQL version may be older than those found on the PostgreSQL website, but this is the simplest way to install on these distributions.

To install PostgreSQL server, update your computer's local package cache with the latest set of packages. Afterwards, install the postgresql package:

```java
sudo apt update
sudo apt install postgresql
```

By default, PostgreSQL is configured to use peer authentication, which allows users to log in if their operating system user name matches a PostgreSQL internal name.

The installation process created an operating system user called postgres to match the postgres database administrative account. To log into PostgreSQL with the psql client, use sudo to run the command as the postgres user:

```java
sudo -u postgres psql
```

When you are finished, you can exit the psql session by typing:

```java
\quit
```

### Changing the Password

With a connection now established to Postgres at the psql prompt, issue the ALTER USER command to change the password for the postgres user:

```java
postgres=# ALTER USER postgres PASSWORD 'myPassword';
```

Output

```java
ALTER ROLE
```

If successful, Postgres will output a confirmation of ALTER ROLE as seen above.

Finally, exit the psql client by using the \q command.

```java
postgres=# \q
```

You’re all done. The default postgres user now has a password associated with the account for use in your other applications.

## Relational databases - TypeScript - PostgreSQL

Learn how to add Prisma to an existing Node.js or TypeScript project by connecting it to your database and generating a Prisma Client for database access. The following tutorial introduces you to the Prisma CLI, Prisma Client, and Prisma Introspection.

### Prerequisites

In order to successfully complete this guide, you need:

- an existing Node.js project with a package.json
- Node.js installed on your machine
- a PostgreSQL database server running and a database with at least one table

See System requirements for exact version requirements.

Make sure you have your database connection URL (that includes your authentication credentials) at hand! If you don't have a database server running and just want to explore Prisma, check out the Quickstart.

## Set up Prisma

As a first step, navigate into your project directory that contains the package.json file.

Next, add the Prisma CLI as a development dependency to your project:

```java
npm install prisma --save-dev
```

You can now invoke the Prisma CLI by prefixing it with npx:

```java
npx prisma
```

Next, set up your Prisma project by creating your Prisma schema file template with the following command:

```java
npx prisma init
```

Output

```java
✔ Your Prisma schema was created at prisma/schema.prisma
  You can now open it in your favorite editor.

warn Prisma would have added DATABASE_URL but it already exists in .env
warn You already have a .gitignore. Don't forget to exclude .env to not commit any secret.

Next steps:
1. Set the DATABASE_URL in the .env file to point to your existing database. If your database has no tables yet, read https://pris.ly/d/getting-started
2. Set the provider of the datasource block in schema.prisma to match your database: postgresql, mysql, sqlite, sqlserver, mongodb or cockroachdb (Preview).
3. Run prisma db pull to turn your database schema into a Prisma schema.
4. Run prisma generate to generate the Prisma Client. You can then start querying your database.

More information in our documentation:
https://pris.ly/d/getting-started
```

This command does two things:

- creates a new directory called prisma that contains a file called schema.prisma, which contains the Prisma schema with your database connection variable and schema models
- creates the .env file in the root directory of the project, which is used for defining environment variables (such as your database connection)

## Install Prisma Client

https://www.prisma.io/docs/getting-started/setup-prisma/add-to-existing-project/relational-databases/install-prisma-client-typescript-postgres

TypeScript - PostgreSQL

### Install and generate Prisma Client

To get started with Prisma Client, you need to install the @prisma/client package:

```java
npm install @prisma/client
```

Notice that the @prisma/client node module references a folder named .prisma/client. The .prisma/client folder contains your generated Prisma client, and is modified each time you change the schema and run the following command:

```java
npx prisma generate
```

Output

```java
Environment variables loaded from .env
Prisma schema loaded from prisma/schema.prisma

✔ Generated Prisma Client (3.14.0 | library) to ./node_modules/@prisma/client in 387ms
You can now start using Prisma Client in your code. Reference: https://pris.ly/d/client
```

```java
import { PrismaClient } from '@prisma/client'
const prisma = new PrismaClient()

```

This command reads your Prisma schema and generates your Prisma Client library

## Querying the database

## Write your first query with Prisma Client

Now that you have generated the Prisma Client, you can start writing queries to read and write data in your database.

If you're building a REST API, you can use Prisma Client in your route handlers to read and write data in the database based on incoming HTTP requests. If you're building a GraphQL API, you can use Prisma Client in your resolvers to read and write data in the database based on incoming queries and mutations.

For the purpose of this guide however, you'll just create a plain Node.js script to learn how to send queries to your database using Prisma Client. Once you have an understanding of how the API works, you can start integrating it into your actual application code (e.g. REST route handlers or GraphQL resolvers).

Create a new file named index.ts and add the following code to it:

```java
//index.ts
import { PrismaClient } from '@prisma/client'

const prisma = new PrismaClient()

async function main() {
  // ... you will write your Prisma Client queries here
}

main()
  .catch((e) => {
    throw e
  })
  .finally(async () => {
    await prisma.$disconnect()
  })
```

Here's a quick overview of the different parts of the code snippet:

- Import the PrismaClient constructor from the @prisma/client node module
- Instantiate PrismaClient
- Define an async function named main to send queries to the database
- Call the main function
- Close the database connections when the script terminates

Depending on what your models look like, the Prisma Client API will look different as well. For example, if you have a User model, your PrismaClient instance exposes a property called user on which you can call CRUD methods like findMany, create or update. The property is named after the model, but the first letter is lowercased (so for the Post model it's called post, for Profile it's called profile).

The following examples are all based on the models in the Prisma schema.

Inside the main function, add the following query to read all User records from the database and print the result:

```java
// index.ts
async function main() {
  const allUsers = await prisma.user.findMany()
  console.log(allUsers)
}
```

Now run the code with your current TypeScript setup. If you're using ts-node, you can run it like this:

```java
npx ts-node index.ts
```

This will print an array of User records as plain old JavaScript objects.

## Write data into the database

The findMany query you used in the previous section only reads data from the database. In this section, you'll learn how to write a query to write new records into the Post and User tables.

Adjust the main function to send a create query to the database:

```java
//index.ts
async function main() {
  await prisma.user.create({
    data: {
      name: 'Alice',
      email: 'alice@prisma.io',
      posts: {
        create: { title: 'Hello World' },
      },
      profile: {
        create: { bio: 'I like turtles' },
      },
    },
  })

  const allUsers = await prisma.user.findMany({
    include: {
      posts: true,
      profile: true,
    },
  })
  console.dir(allUsers, { depth: null })
}
```

This code creates a new User record together with new Post and Profile records using a nested write query. The User record is connected to the two other ones via the Post.author ↔ User.posts and Profile.user ↔ User.profile relation fields respectively.

Notice that you're passing the include option to findMany which tells Prisma Client to include the posts and profile relations on the returned User objects.

Run the code with your current TypeScript setup. If you're using ts-node, you can run it like this:

```java
npx ts-node index.ts
```

Before moving on to the next section, you'll "publish" the Post record you just created using an update query. Adjust the main function as follows:

```java
//index.ts
async function main() {
  const post = await prisma.post.update({
    where: { id: 1 },
    data: { published: true },
  })
  console.log(post)
}
```

Run the code with your current TypeScript setup. If you're using ts-node, you can run it like this:

```java
npx ts-node index.ts
```

# Getting started

This is a sample of how you can easily seed relational data using [Prisma](https://www.prisma.io/). This assumes that you've got a PostgreSQL database created and have some working knowledge of Prisma. If you are using a different SQL database other than PostgreSQL, see below for further instructions.

For more information on getting started, check out the official [Prisma guide](https://www.prisma.io/docs/getting-started).

## Installation

- Run `npm install` or `yarn install`
- Create a `.env` file in the root of the project. You can use the `.env.example` file as an example of what it should look like.
- Inside of your `.env` file, point your `DATABASE_URL` variable to a fresh PostgreSQL database of your choice. **NOTE**: this will wipe out any existing data in the database you point to, so make sure you set up a fresh database for this example!

## Using this with a different SQL database other than PostgreSQL

If you are using a different database other than PostgreSQL, modify the provider at the top of the `prisma/schema.prisma` file.

## Running the seed

- Use the command `npm run seed` or `yarn seed`

```java
npm run seed
```

## Viewing your seed data

- Use the `prisma studio` command

## Further reading

You for additional reading, you can check out my full blog post [here](https://stackfive.io/blog/seeding-relational-data-with-prisma).
