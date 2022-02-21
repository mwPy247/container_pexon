# Create a simple container from an official image
1. Install docker: see website
    => https://docs.docker.com/desktop/mac/install/
2. Verify docker installation: `docker --version`
3. Download latest Postgres image: `docker pull postgres:latest`
4. The container can be run like this: `docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres`
    => https://hub.docker.com/_/postgres

# Interact with the container
1. Enter the shell of the container `docker exec -it some-postgres bash`
    1. Enter the database shell: `psql -U postgres`
    2. Create a table: `CREATE TABLE test_table (id INTEGER PRIMARY KEY, value CHARACTER VARYING(30) NOT NULL);`
    3. Verify that the table was created: `\dt`
    4. Insert data into test table: `INSERT INTO test_table (id, value) VALUES (1, 'test');`
    5. Verify: `SELECT * FROM test_table;`
    6. Exit db shell: `exit;`
2. Exit container: `exit `
3. Have a look at the logs of the container: `docker logs some-postgres`
