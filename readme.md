This repo compares the top three batteries included fullstack web frameworks:
**Ruby on Rails**, **Django**, and **Laravel**.

The goal is not to determine the best framework, but to have a basic understanding of all three frameworks from one
place.


## Table of Contents
1. [Founded](#Founded)
2. [Popularity](#Popularity)
3. [Marketing & Community](#Marketing-&-Community)
4. [Funding](#Funding)
5. [Architecture](#Architecture)
6. [ORM](#ORM)
7. [Database Migrations](#Database-Migrations)
8. [Routing](#Routing)
9. [Project Structure](#Project-Structure)
10. [Template Engine](#Template-Engine)
11. [Authentication](#Authentication)
12. [API Development](#API-Development)
13. [Admin Interface](#Admin-Interface)
14. [Testing](#Testing)
15. [Asynchronous Processing](#Asynchronous-Processing)
16. [Community and Ecosystem](#Community-and-Ecosystem)
17. [Learning Curve](#Learning-Curve)
18. [Performance](#Performance)
19. [Scalability](#Scalability)
20. [Deployment Ease](#Deployment-Ease)

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

## Database Migrations

**Laravel** uses the Artisan command-line tool for migrations.

**Django** uses `makemigrations` and `migrate` commands,

**Ruby on Rails** has its own migration system.

It was Ruby on Rails who pioneered the concept of database migrations in web frameworks.

Django automates migrations throught its ORM. A django developer in most cases would simply edit models.py, and run
makemigrations and migrate to update the schema without any manual migration file creation.

Laravel and Rails lack automated ORM migrations but offer streamlined processes as well. Laravel provides easier
rollbacks and seeding. Rails features reversible migrations and detailed generators.

## Routing

Rails has a single routes.rb file. The naming conventions are similar to Laravel.

Django uses multiple urls.py files within its apps, and is mapped to a view function or class.

Laravel typically uses files in the routes directory and allows middleware to be assigned in the route definition
contrary to Django and Rails.

## Project Structure

Django follows a project-and-app structure. The main project and its multiple apps would each have its own urls,
templates and static files directories.

Laravel uses a centralized approach, with application logic residing in the `app/` directory. Configuration files are
separate, and views are stored in `resources/`.

Rails adopts a convention-over-configuration philosophy, with a predefined directory structure. Models, views, and
controllers are organized in their respective folders within the `app/` directory.

Django's app-driven model is about creating modular, reusable 'apps' which can be plugged into different projects
seamlessly. Laravel and Rails are more about a centralized approach to application development.

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

**Laravel** and **Ruby on Rails** are generally considered easier for beginners. **Django** has a steeper initial
learning curve but offers powerful capabilities once mastered. Laravel and Rails are seen as more beginner-friendly,
while Django's explicitness can be initially challenging but leads to a deeper understanding.

## Performance

All three frameworks perform well when optimized. **Django** often edges out for database-intensive operations. *
*Laravel** has tools like Laravel Octane for optimization, and **Ruby on Rails** has focused on performance improvements
in recent versions.

## Scalability

All three frameworks can scale effectively with proper architecture. **Django** and **Ruby on Rails** have more
high-profile, high-traffic use cases demonstrating their scalability.

## Deployment Ease

**Laravel** offers managed services like Forge and Vapor for easy deployment. **Django** deployment can be more
challenging but is supported by tools like Gunicorn and WSGI. **Ruby on Rails** pioneered easy deployment with Heroku
and has many established deployment patterns.