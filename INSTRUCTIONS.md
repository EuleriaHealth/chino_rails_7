# [COMMUNITY] Chino Ruby SDK <!-- omit in toc -->

Ruby SDK for Chino.io API

**Community SDK:** Most of the content and the code has been provided 
by third-parties.

For issues or questions, please contact [tech-support@chino.io](mailto:tech-support@chino.io).

-------------------------------------------------------------------------------
#### Table of content <!-- omit in toc -->
- [Installation and setup](#installation-and-setup)
- [SDK usage](#sdk-usage)
- [Development](#development)
  - [Running the tests](#running-the-tests)
- [License](#license)

-------------------------------------------------------------------------------

## Installation and setup

Please refer to [README.md](./README.md#requirements)

## SDK usage

*Read the [full API docs](https://console.test.chino.io/docs/v1)*

For usage details and a basic example, please refer to 
[README.md](./README.md#usage)

## Development
Some useful commands to use for local development. 
See also [CONTRIBUTING.md](./CONTRIBUTING.md)

### Install locally <!-- omit in toc -->

    bundle exec rake install

### Running the tests
You have to run the following commands in the terminal in order to 
run the tests:

    bundle install
    cd test  # optional since version 3.0.0
    bundle exec ruby sdk_test.rb

### Release a new version (mostly for internal use) <!-- omit in toc -->

- update the version number in `lib\chino_ruby\version.rb`
- run 

        bundle exec rake release

    This will create a git tag for the version.
- push git commits and tags
- push the `.gem` file to [rubygems.org](https://rubygems.org)

## License

The gem is available as open source under the terms of the 
[MIT License](http://opensource.org/licenses/MIT).