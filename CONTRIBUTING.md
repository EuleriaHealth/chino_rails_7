# Contributing

For suggestions, improvements or bug fixes please follow these steps:

- fork the repository. Remember to append your name to the list of contributors
  in the [authors file](./AUTHORS.md)
  
- run `bin/setup` to install dependencies.
  
  You can also run `bin/console` for an interactive prompt that will allow
  you to experiment.
  
- develop. If you are adding new logic, **write tests** for it.
  
- launch tests - :warning: **be careful!**:
  
    > the tests will **delete EVERYTHING stored in the account** in order
    to preserve the correctness of the tests. Run them on a custom account
    and always against the test API `https://api.test.chino.io`.

- create a Merge Request to the original repository.
