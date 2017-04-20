# flyway-spike

Demonstrates using pure SQL to drive migrations in [Flyway](https://flywaydb.org/).

### How to run this project

Simply run `mvn clean compile flyway:migrate`.  The `target` directory will appear with an extensionless sqlite db file called `foobar`.  It can be accessed with sqlite if you have it installed: `sqlite ./target/foobar`.

You can also run `mvn clean compile flyway:migrate -P cucumber`, which activates the Cucumber maven profile.  This will demonstrate running the main migrations plus test migrations.  Test migrations are useful for pre-loading the database with fake data for integration testing.

If an error occurs, make sure you are using Java 8.  You can also run run the command in error mode, to show stack traces and so forth: `mvn -e clean compile package flyway:migrate`


### Stuff

The main migrations, written in pure SQL, can be found in `src/main/resources/db/migration`.

The test migrations can be found in`src/test/resources/db/migration`.

Please be sure to read [the documentation on SQL-based migrations](https://flywaydb.org/documentation/migration/sql).