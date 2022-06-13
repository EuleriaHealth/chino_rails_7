# [COMMUNITY] Chino Ruby SDK <!-- omit in toc -->
[![Gem Version](https://badge.fury.io/rb/chino_ruby.svg)](https://rubygems.org/gems/chino_ruby)

Ruby SDK for Chino.io API

**Community SDK:** Most of the content and the code has been provided 
by third-parties.

**Version**: `3.0.0`
 
**Useful links**
 - [Full SDK instructions](./INSTRUCTIONS.md)
 - [Chino.io API docs](http://console.test.chino.io/docs/v1)

For issues or questions, please contact [tech-support@chino.io](mailto:tech-support@chino.io).

-------------------------------------------------------------------------------
#### Table of content <!-- omit in toc -->
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
  - [Basic example](#basic-example)

-------------------------------------------------------------------------------

## Requirements

- Ruby - [Download](https://www.ruby-lang.org/en/)

- Once you got the Ruby runtime, you may want to install the Bundler 
  package manager which allows to run the `bundle` commands:

        gem install bundler

## Installation

- Copy file `config-chino-base.yml` to `config-chino.yml`.
  
    Insert the credentials from your account on the Chino.io platform.
    **Do not commit this file** in git!

- Install the dependencies using one of the following methods:

   - Add this line to your application's Gemfile:

      ```ruby
      gem 'chino_ruby'
      ```

      And then execute:

          bundle

  - Install with:

          gem install chino_ruby

  - Run 

          bundle exec rake install

## Usage

Initialize a Chino.io client variable as follows:

```ruby
@client = ChinoAPI.new("<your-customer-id>", "<your-customer-key>", "<server-url>")
```

The Customer ID and Key are provided with your account for the Chino.io 
platform.

The server URL must be one of:
- `https://api.test.chino.io/v1` for the **Test API**
- `https://api.chino.io/v1` for the **Production API**
  
Once you created your client instance, you can use it to call 
functions and communicate with the server.  

### Basic example
Let's create a *Document* on Chino.io:

1. Create a *Repository*
   
    ```ruby
    @repo = @client.repositories.create_repository("test repo description")
    ```

2. Create a *Schema* inside the *Repository*

    ```ruby
    fields = []
    fields.push(Field.new("string", "test_string", true))
    fields.push(Field.new("integer", "test_integer", true))

    @schema = @client.schemas.create_schema(@repo.repository_id, "test schema description", fields)
    ```

3. Finally, create the *Document* inside the *Schema*

    ```ruby
    content = Hash.new
    content["test_string"] = "sample value ruby"
    content["test_integer"] = 123

    @doc = @client.documents.create_document(@schema.schema_id, content)
    ```
