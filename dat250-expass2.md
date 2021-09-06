# DAT250-expass-2
_DAT250: Software Technology Experiment Assignment 2_

### Technical problems that you encountered during installation and use of Java Persistence Architecture (JPA) and how you resolved

The installation and usage of JPA when fine. Some minor issues getting IntelliJ to run the code, but it was just some minor config errors in the IDE.

### A link to your code for experiments 1 and 2 above

Screenshot for experiment 1 can be found together with the code for experiment 2. It is named `expirement-1__generated-tables.png`.

[Link to repository containing Experiment 2](https://github.com/palexcast/DAT250-expass-2)

### An explanation of how you inspected the database tables and what tables were created. For the latter, you may provide screenshots.

I used IntelliJs built in Database connector to inspect the DB and the tables in it.

Screenshot of tables after adding new models is named `experiment-2__generated-tables.png`

To verify that the relations are there, you could view the many-to-many tables and see that the ids correlate.

I also ran a quick "print" method to get the following
```
Person(id=1, name=Max Mustermann, creditCards={[CreditCard(id=2, number=12345, limit=-10000, balance=-5000, bank=Bank(id=1, name=Pengebank, creditCards={IndirectList: not instantiated}), pincode=Pincode(id=1, pincode=123, count=1)), CreditCard(id=1, number=12345, limit=-10000, balance=-5000, bank=Bank(id=1, name=Pengebank, creditCards={IndirectList: not instantiated}), pincode=Pincode(id=1, pincode=123, count=1))]}, address={[Address(id=1, street=Inndalsveien, number=28, persons={IndirectList: not instantiated})]})
```

Some of the values say `IndirectList: not instantiated}` this is due to lazy-loading. For the example I manually triggered some of the lists to be fetched, for this example.

### Any pending issues with this assignment that you did not manage to solve

None