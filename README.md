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

# vercel --prod --confirm
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

## Viewing your seed data

- Use the `prisma studio` command

## Further reading

You for additional reading, you can check out my full blog post [here](https://stackfive.io/blog/seeding-relational-data-with-prisma).
