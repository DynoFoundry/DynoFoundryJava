# DynoFoundry for Java

> Because it's a tough world out there. At least, querying dynamodb should be easy.

DynoFoundry tucks away the rather verbose and often alien APIs exposed by AWS for interfacing Dynamodb with Java. It also takes care of many of the *eccentirities* of dynamodb itself. (For example, returning empty pages if no items pass the filter!)


## What to Expect

```java
var query = dynoFoundry.query(CollectedType.class)
                      .table("user")
                      .secondaryIndex("date_registered_index")
                      .partitionKey("self_onboarded")
                      .sort("date_registered", DynoFoundryDirection.ASC)
                      .filter("first_name = :first_name:s AND last_name = :last_name:s", first_name, last_name)
                      .limit(10)
                      .paginationToken(nullableTokenFromPreviousQuery)
                      .projection("first_name", "age", "last_login")
                      .execute();
```

## Status of the Project

POC is underway. Check out the [feat/poc](https://github.com/DynoFoundry/DynoFoundryJava/tree/feat/poc) branch.

## Being Used by

WIP

## LICENSE

[MIT LICENSE](./LICENSE)

## Authors

WIP


