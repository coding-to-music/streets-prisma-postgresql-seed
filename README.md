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
