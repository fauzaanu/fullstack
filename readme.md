This repo compares the top three batteries included fullstack web frameworks:
**Ruby on Rails**, **Django**, and **Laravel**.

The goal of this repo is to provide a basic understanding of all three frameworks from one place.


## Table of Contents
1. [Founded](#Founded)
2. [Popularity](#Popularity)
3. [Marketing & Community](#Marketing-&-Community)
4. [Funding](#Funding)
5. [Architecture](#Architecture)
6. [ORM](#ORM)
7. [Database Migrations](#Database-Migrations)
8. [Forms](#Forms)
9. [Routing](#Routing)
10. [Project Structure](#Project-Structure)
11. [Template Engine](#Template-Engine)
12. [Authentication](#Authentication)
13. [API Development](#API-Development)
14. [Admin Interface](#Admin-Interface)
15. [Testing](#Testing)
16. [Asynchronous Processing](#Asynchronous-Processing)
17. [Community and Ecosystem](#Community-and-Ecosystem)
18. [Learning Curve](#Learning-Curve)
19. [Performance](#Performance)
20. [Scalability](#Scalability)
21. [Deployment Ease](#Deployment-Ease)

## Founded

**Ruby on Rails** was created by David Heinemeier Hansson in 2004.

**Django** was created by Adrian Holovaty and Simon Willison in 2005.

**Laravel** was created by Taylor Otwell in 2011.

## Popularity

**Laravel** has 77.5k+ stars on GitHub.

**Django** has 77.9k+ stars.

**Ruby on Rails** has 55.3k+ stars.

## Marketing & Community

**Laravel** has an active and energetic community. An influencial developer and a company behind it.

**Django** has the most silent and calm community. The creators are hardly known to the users of the framework and there
is no company with commercial intentions.

**Ruby on Rails** has an active community. Both the creator and the company behind it are known to the users and have
great influence on the community.

## Funding

**Laravel** generates revenue through the sale of commercial products like Forge, Envoyer, Nova, and Spark, in addition
to sponsorships and donations.

**Django** operates solely through donations and sponsorships to a non-profit foundation, the Django Software
Foundation.

**Ruby on Rails** receives funding from its parent company, 37Signals, and contributions from its community and
sponsors.

## Architecture

**Laravel** and **Ruby on Rails** follow the traditional MVC (Model-View-Controller) pattern,

**Django** uses MTV (Model-Template-View) pattern, which is similar but emphasizes templates.

The key difference is that Django's "View" takes on the role of the Controller, while its "Template" handles the
presentation logic that would typically be in the View of an MVC framework.

This separation in Django can lead to cleaner, more focused code by clearly distinguishing between request handling
logic (Views) and presentation logic (Templates).

## ORM

**Laravel** uses Eloquent, which follows the Active Record pattern.

**Django** uses its own ORM that follows the Data
Mapper pattern.

**Ruby on Rails** also uses the Active Record pattern.

Learn more from the book, [Patterns of Enterprise Application Architecture](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420) where Martin Fowler coined the terms [Active Record](https://en.wikipedia.org/wiki/Active_record_pattern) and [Data Mapper patterns](https://en.wikipedia.org/wiki/Data_mapper_pattern).

## Database Migrations

**Laravel** uses the Artisan command-line tool for migrations.

**Django** uses `makemigrations` and `migrate` commands,

**Ruby on Rails** has its own migration system.

It was Ruby on Rails who pioneered and popularized the concept of database migrations in web frameworks.

Django has automated migrations
_Django automates migrations by making migrations be a replica of the models.py file within each of the apps. The state of the current database schema can be observed from models.py at all times. Automating stuff through ORM is common in django and is also present in 
model forms._

## Forms

Django comes with model forms, Another area where django automates through its ORM. Forms are generated as a replica of all the fields on the database and comes with built in form validation. To get models forms working very little code is needed. The amount of code written is further reduced through generic views in django.

_Generic views in django are views provided by the framework for really common operations (eg: CRUD). Connecting the view to a model and adding a template is the only code that is written in this case. The development speedups that django provides through generic views are really useful for MVPs and hackathons_

Ruby on rails have form_for helper which generates a form html based on models, quite like django forms and includes validation as well. Rails require a little bit more manual effort than django however to get it setup.

Laravel unlike rails and django lacks tight integration between models and forms. Laravel Collective provides a form builder package for easier form creation. There are third party packages in Laravel ecosystem that implements django model forms. Laravel does offer good form validation and handling capabilities.

## Routing

Rails has a single routes.rb file.
Laravel uses files within the routes directory for routes.
Django uses multiple urls.py files within its apps, and is mapped to a view

Laravel allows middleware to be assigned in the route definition contrary to rails and django

## Project Structure

Django follows a project and app structure. Each project would have multiple apps. 
Each app would have their own static files, templates, urls, views, models and even the database migrations.
Project would also have a urls.py file which connects all the apps by including their routes.
This app driven structure in django speeds up development due to it being really easy to jump around code, making reusable apps, etc.

```
finance_project/
│
├── finance_project/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── income/
│   ├── migrations/
│   ├── static/
│   ├── templates/
│   │   └── income/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
│
├── expense/
│   ├── migrations/
│   ├── static/
│   ├── templates/
│   │   └── expense/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
│
├── templates/
│   └── base.html
│
├── static/
│
├── manage.py
└── requirements.txt
```

Ruby on Rails follows a convention-over-configuration approach with a well-defined project structure. A Rails application is organized into several directories, including app (containing models, views, controllers, helpers, and assets), config (for routes, database configuration, and environments), db (for database migrations and seeds), and test (for unit and integration tests). The app directory is further subdivided to separate concerns, with models handling data and business logic, controllers managing request flow, and views rendering the user interface. Rails uses a centralized routing system in config/routes.rb to map URLs to controller actions. This structured approach promotes code organization, maintainability, and adherence to the MVC (Model-View-Controller) pattern, allowing developers to quickly navigate and understand the codebase.

```
finance_app/
│
├── app/
│   ├── controllers/
│   │   ├── incomes_controller.rb
│   │   └── expenses_controller.rb
│   ├── models/
│   │   ├── income.rb
│   │   └── expense.rb
│   ├── views/
│   │   ├── incomes/
│   │   ├── expenses/
│   │   └── layouts/
│   ├── helpers/
│   └── assets/
│
├── config/
│   ├── routes.rb
│   └── database.yml
│
├── db/
│   └── migrations/
│
├── lib/
│
├── log/
│
├── public/
│
├── test/
│
├── vendor/
│
├── Gemfile
└── Rakefile
```

Laravel, employs a modular and intuitive project structure. The main application logic resides in the app directory, which contains subdirectories for HTTP controllers, models, and various service classes. Views are stored in the resources/views directory, while routes are defined in the routes directory, typically separated into web.php for web routes and api.php for API routes. Laravel uses a powerful ORM called Eloquent, with model classes typically placed in app/Models. The database directory houses migrations and seeders for database management. Public assets are stored in the public directory, while configuration files are located in the config directory. Laravel's structure encourages the use of service providers and facades for extending functionality, promoting a clean and modular codebase that's easy to maintain and scale.

```
finance_app/
│
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── IncomeController.php
│   │   │   └── ExpenseController.php
│   │   └── Requests/
│   ├── Models/
│   │   ├── Income.php
│   │   └── Expense.php
│   └── Providers/
│
├── config/
│
├── database/
│   ├── migrations/
│   └── seeders/
│
├── public/
│
├── resources/
│   ├── views/
│   │   ├── incomes/
│   │   ├── expenses/
│   │   └── layouts/
│   ├── lang/
│   └── js/
│
├── routes/
│   ├── web.php
│   └── api.php
│
├── storage/
│
├── tests/
│
├── vendor/
│
├── .env
├── artisan
├── composer.json
└── package.json
```

## Template Engine

**Laravel** uses Blade

**Django** uses the Django Template Language (DTL)

**Ruby on Rails** uses ERB (Embedded Ruby).

Blade and ERB allow language code within templates, offering flexibility and ease. DTL is highly restrictive yet
understanding the difference in MTV and MCV helps understand the design philosophy behind it.

## Authentication

**Django** includes a comprehensive built-in authentication system that handles user accounts, groups, permissions, and
cookie-based user sessions. It's highly customizable and integrates seamlessly with Django's admin interface.

**Laravel** provides a full authentication system out of the box with the `auth` scaffolding. It includes features like
registration, login, password reset, and email verification. Laravel also has multiple first-party packages related to
authentication.

**Ruby on Rails** doesn't have a built-in authentication system, but commonly uses the Devise gem. Devise is a flexible
authentication solution that provides a full MVC solution based on Warden. It offers modules for various authentication
strategies, including database authentication, OAuth, and LDAP.

All three frameworks support customization to meet specific project requirements, including role-based access control
and API authentication methods like JWT.

## API Development

**Laravel** uses Sanctum for API authentication, which focuses on simplicity.

**Django** has the comprehensive Django REST Framework (DRF) but it is not built-in.

**Ruby on Rails** uses Active Model Serializers for API development, which is lightweight but extensible.

## Admin Interface

**Django** has a built-in, customizable admin interface, which is a standout feature offering immediate productivity
gains.

**Laravel** and **Ruby on Rails** rely on packages or gems for admin interfaces. Laravel has multiple first-party
packages for admin panels, like Nova and Voyager.

## Testing

**Laravel** uses PHPUnit with Laravel-specific assertions

**Django** has a built-in test framework based on unittest,

**Ruby on Rails** uses Minitest by default, with RSpec as a popular alternative. All three frameworks provide
comprehensive testing tools, with Rails having a particularly rich testing ecosystem.

## Asynchronous Processing

**Laravel** has a well-integrated queue system with various drivers.

**Django** uses third-party solutions like Celery
or Huey, with a native task backend currently in development.

**Ruby on Rails** provides Active Job with various backends for background processing.

## Community and Ecosystem

All three frameworks have large, active communities. **Ruby on Rails** benefits from its maturity and a vast ecosystem
of gems. **Laravel** is known for rapid adoption of new features, and **Django** has a focus on stability.

## Learning Curve

**Laravel** and **Ruby on Rails** are generally considered easier for beginners. 

**Django** has a steeper initial learning curve but offers powerful capabilities with a lot of productivity gains once mastered.

## Performance

All three frameworks perform well when optimized.

**Django** often edges out for database-intensive operations. 

**Laravel** has tools like Laravel Octane for optimization, and **Ruby on Rails** has focused on performance improvements in recent versions.

## Scalability

All three frameworks can scale effectively with proper architecture.

**Django** and **Ruby on Rails** have more high-profile, high-traffic use cases demonstrating their scalability.

1. Instagram - Django - [Carl Meyer about Django @ Instagram at Django: Under The Hood 2016](https://youtu.be/lx5WQjXLlq8)
2. Shopify - Rails - [RailsConf 2022 - Shopify](https://youtu.be/p_C6BcKX0qs?list=PLr8d6l1sJufdKr-d_SG7lrycsHwMMEDPl)
3. ...


## Deployment Ease

**Laravel** offers managed services like Forge and Vapor for easy deployment. 

**Django** as a framework does not offer much assitance when it comes to deployment. 
Some popular solutions include cookie-cutter django and the many different dockerrized templates. 
Deploying django to [railway](https://railway.app?referralCode=NC4Tt6) is one of the most simple and fast aproach. (Dockerization not nessesary due to NIXPACKS)

**Ruby on Rails** has many established deployment patterns.
