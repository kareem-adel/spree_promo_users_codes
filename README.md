SpreePromoUsersCodes
=====================

SpreePromoUsersCodes is an extension which helps an admin to generate customized coupon codes for a promotion for their customers. It enables the admin to create coupon codes for each promotion by marking it as multi-coupon and creating unique codes for the customers he/she wants to send the codes to. These codes can only be used once. The codes are e-mailed to the customer so the code is known only to him/her.

Installation
------------

1. Add this extension to your Gemfile:

  #### Spree >= 3.3

  ```ruby
  gem 'spree_promo_users_codes', github: 'vinsol-spree-contrib/spree_promo_users_codes', branch: 'master'
  ```

  #### Spree < 3.3

  ```ruby
  gem 'spree_promo_users_codes', github: 'vinsol-spree-contrib/spree_promo_users_codes', branch: 'X-X-stable'
  ```

  The `branch` option is important: it must match the version of Spree you're using.
  For example, use `3-0-stable` if you're using Spree `3-0-stable` or any `3.0.x` version.


2. Bundle your dependencies and run the installation generator:

  ```shell
  bundle
  bundle exec rails g spree_promo_users_codes:install
  ```


Usage
-----

It creates a new CRUD for promotion codes. Every promotion that is marked as multi-coupon can have a unique code for each customer of the site.

The codes are non-editable, so once generated, a code remains in existence unless explicitly destroyed by the admin. Usage rules are same as those for promotions. If there is no usage limit, any number of codes can be created; but, if there is a usage limit on the promotion, only those many coupon codes can be validated. Please note that the generated codes are one-time usable, and only by the designated customer.


Testing
-------

  #### Spree >= 3.1

  For Building Dependencies:
  ```shell
  appraisal install
  ```

  The dummy app can be regenerated by using:
  ```shell
  appraisal spree-3-1 rake test_app

  ```
  This will run rake test_app using the dependencies configured for Spree 3.1. Similarly you can use spree-3-2 and spree-master for generating dummy applications using dependencies for Spree 3.2 and latest version of Spree


  ```shell
  appraisal spree-3-1 rspec
  ```
  This will run rspec using the dependencies configured for Spree 3.1. Similarly you can use spree-3-2 and spree-master to run rspec using dependencies for Spree 3.2 and latest version of Spree


  #### Spree 3.0 and Spree 2.x

  First bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run specs. The dummy app can be regenerated by using `rake test_app`.

  ```shell
  bundle
  bundle exec rspec spec
  ```


Contributing
------------

  1. Fork the repository.
  2. Clone your repository.
  3. Run `bundle install`.
  5. Make the required changes.
  6. Ensure all specs are passing.
  7. Submit your pull request.


Copyright (c) 2017 VinSol, released under the New BSD License.
