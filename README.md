# Overview

Ready to accelerate your enterprise software development teams and deliver successful software projects? Welcome to the Optivem Framework.

## What is the Optivem Framework?

Optivem Framework is a high-quality high-performance architecture framework built for software enterprise teams. It is rooted in best practices in enterprise architecture, providing a standardized software solution template. This provides your software teams with a clean architecture foundation, so that they can quickly and easily build quality software - accelerate your development whilst retaining high quality.

Optivem Framework is open source \(MIT licence\) so it can be freely used both for commercial and non-commercial purposes.

## Which technologies does the Optivem Framework support?

Currently, the Optivem Framework is focused on backend web development and it targets .NET Core 2.2 \(soon we will be upgrading to .NET Core 3\). In the future, we also have plans to support Java web applications.

Furthermore, aside from backend web development, we also intended to provide frontend development templates \(Angular\) .

## What results does the Optivem Framework provide?

Optivem Framework is designed to support your software teams:

* Develop high quality & high performance software
* Develop software faster than ever before
* Develop software in a standardized way
* Easily grow your teams with new members

Optivem Framework is designed to support your organization:

* Deliver on time & budget
* Increase profitability & decrease costs
* Make your customers happy

## What are the key principles of the Optivem Framework?

Optivem Framework is founded upon the following three principles:

1. **Quality principle**: Quality software is a prerequisite for producing software which works well, with minimal defects and with low maintenance costs, and overall providing a good customer experience. When projects don't start with a quality architecture and accumulate technical debt over time, it reaches a point when there are too many bugs, the software is unusable, new features cause system breakdown, developers lose productivity and overall leading to customer dissatisfaction. It is essential that projects are started with a solid quality architectural foundation - this is exactly the core focus of the Optivem Framework, to help you develop modular, flexible, extensible and maintainable software.
2. **Speed principle**: However, even though we recognize the importance the importance of quality, we are also familiar with the time pressures faced in software projects - to deliver early, to deliver fast, whereby in reality, in the short-term, development speed becomes more important than quality, even though quality is essential for long-term development speed. This is a major barrier for organizations looking to setup quality system architecture. This is where Optivem Framework comes in - it provides a template for the solution architecture as well as components to reduce development time.
3. **Standardization principle**: Last, but not least we come to standardization - the principle to standardize project structure so that we can systemically achieve quality and speed across our software projects. This also increases re-use and provides organizations with higher flexibility to organize development teams and incorporate new members, and avoids to the "re-invent the wheel" syndrome. It also makes project success a part of the organization, rather than relying on a few "talented" "A-player" individuals. Optivem Framework did not invent anything new, it simply took existing best practices and provided a standardized templated solution.

## What are the key features of the Optivem Framework?

* Optivem Framework provides the Optivem Template, which can be installed via NuGet - and after inputting the project name, a new solution will be generated for you with all the architectural layers and with sample code \(customers, products and orders\) which can be used a starting point and practical example for implementation
* Optivem Framework provides standardized implementation for CRUD operations across all layers of the sofware \(from REST controllers, to application services, to repositories\)
* Optivem Framework has pre-packaged popular NuGet packages, including Entity Framework Core 2, FluentAssertions, AutoMapper, MediatR, which are used for implementation in the infrastructure layer - however, these are defaults, so you are not locked in but can choose other packages and provides, because Optivem Framework relies on interfaces so that third party libraries and frameworks are easily swappable
* Optivem Framwork is designed to be high performance, especially efficient operations with  Entity Framework Core 2 - efficiently working with large data sets
* Optivem Framework contains components which simplify automated testing, especially Selenium and REST API testing, so that automated tests can be produced faster and with less code

## How can we use the Optivem Framework for new projects?

The primary intended usage for the Optivem Framework is for building new projects. This is where Optivem Framework provides the most value - in setting a clean architecture foundation. We recommend the following approach:

1. Install the Optivem Template via NuGet [https://docs.optivem.com/framework/development/](https://docs.optivem.com/framework/development/) which creates a new Visual Studio solution, with all the layers: Core Layer, Infrastructure Layer, Web Layer, Test Layer
2. Familiarize yourself with the sample code in the generated solution \(bases on the commonly used example in enterprise software - customers, products and orders\), it contains implementation across all layers: Sample REST controllers in the Web Layer, Sample application services and domain entities in the Core Layer, Sample integration with third-party frameworks \(Entity Framework Core, AutoMapper, FluentAssertions, MediatR\) in the Infrastructure Layer, Sample automated tests \(domain unit tests, application service integration tests, REST API integration tests and Selenium system tests\)
3. Based on the sample code, you can starting applying it to your project - i.e. to create relevant REST controllers, application services, domain entities, etc. by following the standardized structure, and when you're comfortable with that you can later delete the sample code
4. In the case that you want to work with additional third-party libraries or replace the default the default third-party libraries included within the Optivem Framework Infrastructure, you can freely do so, by implementing wrappers for any other third-party libraries

_Note: We are also in the process of releasing automated code generation functionality for the Optivem Framework, whereby it will generate classes for your entities across all layers._

## How can we use the Optivem Framework for existing projects?

A lot of software development revolves in working with existing software systems, by extending them with new features and bug fixing. When working with existing systems, it may be too difficult or risky or expensive to attempt major refactoring or system overhaul, and for that reason we recommend an incremental quality improvement approach using the Optivem Framework:

1. As a first \(less-invasive\) step, you can use the Optivem Framework Infrastructure packages individually - using them as you would use other NuGet libraries - with examples as follows: using the Optivem Framework HTTP clients \(based on System.Net\), Csv Serializers \(based on CsvHelper\), Excel readers and writers \(based on EPPlus\), and generic repository and unit of work implementations \(implemented on top of Entity Framework Core 2\) and system utilities \(working with DataTables, reflection, parsing\), and web utilities \(exception handlers, validation responses, CSV formatters for ASP.NET Core\), and automated testing wrappers \(wrappers for automated web testing based on Selenium\)
2. As a next \(more invasive\) step, you can switch to Domain Driven Design \(DDD\) and use-case driven approach by implementing the interfaces from Optivem Framework Core packages \(Domain and Application\), which would involve refactoring your code into properly separated application services, use cases, entities, value objects, etc.
3. Last, but not least, in cases where changing the existing system is not feasible, we recommend using Optivem Framework when your team is assigned with the next bigger features or modules - to consider implementing them as microservices, using the Optivem Template to create the microservice, whereby the old legacy application can communicate with the new microservice, and gradually other parts of the old application may be migrated too

In summary, Optivem Framework can be used both for new and existing projects - in both cases it will help your team to produce high quality solutions.

## How can Optivem Framework support our senior developers?

Senior developers often have a key role in the design and architecture of software solutions - whether it's for products, projects, or modules. Aside from that, they are also involved in mentoring and supporting junior developers during development as well as code reviews. From technical perspectives, senior developers are key stakeholders in decisions regarding architecture and quality, building code re-usable, collaboration and knowledge sharing.

At some point in time, as teams and companies grow, they reach a point at which senior developers are not just involved in invdividual projects, but also in systematizing and standardizing development across the team - which involves often companies producing internal shared code, internal package manager setup, internal samples and templates, etc. based on best practices and coaching team members to push forward adoption. However, this can a time-consuming process, taking months or years to create the adequate code base, yet alone to implement it in practice. 

Optivem Framework can support senior developers so that next time when they need to setup a new project, that they can get it up and running very fast. It also serves to support them in promoting standardization within the teams.

## How can Optivem Framework support our  junior developers?

Junior developers are an important part of software teams. When junior developers are provided with a solid foundation in software practices and clean code examples, they will be able to contribute with high productivity to software development. This is also an important asset for companies - to be able to grow talent in-house, which can be less expensive and less time-consuming than hiring externally. Over time, these juniors become more experienced and they can mentor and support the next generation of developers.

However, junior developers, a _blank slate_, can be a double-edged sword. On one hand, if junior developers are provided with the right foundation, working on a project which follows best practices, then those juniors can learn by example, and further contribute to the project success. On the other, if junior developers are provided with a poor foundation, working on a project with low quality code, then since this is all they've seen, the poor code will exponentially multiply as the team grows, further decreasing quality and productivity.

This is where Optivem Framework can help - by providing a template for the entire project architecture and with end-to-end sample working code, developed with best practices in mind, it provides junior developers with practical quality examples so that they can follow the template and apply it for new features and functionalities.

## How can Optivem Framework support our test automation engineers?

\(in-progress\)

## How can Optivem Framework support parallel development?

\(in-progress\)

## What are the next steps to implement the Optivem Framework?

Are you an IT Leader who wants to grow high performance teams and deliver successful projects?

{% page-ref page="leadership.md" %}

Are you a Software Architect who wants to design software architecture for maintainable and extensible software systems?

{% page-ref page="architecture.md" %}

Are you a Software Developer who wants to write software faster, with less code and higher quality?

{% page-ref page="development.md" %}

Are you a Test Automation Engineer who wants to write automated tests faster and make them easy to maintain?

{% page-ref page="testing.md" %}

All the best in your journey towards successful IT projects and products - reach the next level with the Optivem Framework.

