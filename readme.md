<p align="center"><img src="https://res.cloudinary.com/dtfbvvkyp/image/upload/v1566331377/laravel-logolockup-cmyk-red.svg" width="400"></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>
  
## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[British Software Development](https://www.britishsoftware.co)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- [UserInsights](https://userinsights.com)
- [Fragrantica](https://www.fragrantica.com)
- [SOFTonSOFA](https://softonsofa.com/)
- [User10](https://user10.com)
- [Soumettre.fr](https://soumettre.fr/)
- [CodeBrisk](https://codebrisk.com)
- [1Forge](https://1forge.com)
- [TECPRESSO](https://tecpresso.co.jp/)
- [Runtime Converter](http://runtimeconverter.com/)
- [WebL'Agence](https://weblagence.com/)
- [Invoice Ninja](https://www.invoiceninja.com)
- [iMi digital](https://www.imi-digital.de/)
- [Earthlink](https://www.earthlink.ro/)
- [Steadfast Collective](https://steadfastcollective.com/)
- [We Are The Robots Inc.](https://watr.mx/)
- [Understand.io](https://www.understand.io/)
- [Abdel Elrafa](https://abdelelrafa.com)
- [Hyper Host](https://hyper.host)

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-source software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## AWS Cloud Deployment Instructions
1. Log into AWS and select Services from the main menu.
2. Select RDS.
3. Under the Create database section click the Create database button.
4. Select the MySQL engine option and the 5.6 version edition radio button. Check the 'Enable options for free tier'. Click the Next button.
5. Fill out the Specify DB details form:
    - From Settings enter DB instance identifier enter instance name (i.e., mydatabaseinstance).
    - From Settings enter Master username and password.
    - Click the Next button.
    - Leave all defaults in the Configure advanced settings form.
6. From the RDS Dashboard select your database instance.
    - Your database URL is listed under the Connect section under the Endpoint value.
    - Make your database accessible from a Java application by clicking the Security groups link under the Details section for the database.
    - In the Security Group setup select the Inbound Tab. Click the Edit button. Under the Source dropdown select the Anywhere option.
    - In MySQL Workbench setup a connection using the AWS Database Endpoint URI and credentials. Create the 'cst-323' schema and tables by running the DDL script created from your development environment.
7. Create and Configure the AWS PHP Application:
    - Update app code in source control:
        ~ It is possible to set environment specific configuration in your .env file for a PHP Laravel project.
    - Log into AWS and select Services from the main menu.
    - Select Elastic Beanstalk service.
    - Click the 'Create new Application' link from the top right menu.
    - Give your Application Name (i.e., TestApp). Click the Create button.
    - Create your Application Environment by clicking the 'Create one now' link.
    - Select the 'Web server environment' and click the Select button.
    - Fill out the following fields in the Creating web server environment form:
        - From Environment Information Domain: Give your Application a name (i.e., test-app).
        - From Base configuration: Select PHP from the Preconfigured platform options. Upload a ZIP file of your PHP application.
        - Click the Create Environment button. Wait for environment to get built.
        - From the Elastic Beanstalk application screen click the App URL to validate application is running properly.
8. Deploy Manually:
    - Create a ZIP file with all your code (make sure to update APP_ENV to amazon in .env).
    - Log into AWS and select Services from the main menu.
    - Select Elastic Beanstalk. Select your Application.
    - Click the Upload and Deploy button. Upload your ZIP file and give your build a label. Click the Deploy button.
9. Deploy using a AWS Code Pipeline:
    - Add a buildspec.yml to the root of your application code.
    - Log into AWS and select Services from the main menu.
    - Select the CodePipeline service.
    - Click the Create Pipeline button.
    - Give your pipeline a name (i.e., TestAppPipeline). Click the Next step button.
    - Select GitHub from the Source provider dropdown. Click the Connect to GitHub button and select your repo and master branch. Click the Next step button.
    - Select AWS CodeBuild from the Build provider dropdown. Select the Create a new build project option. Give your build a name. Select Ubuntu operating system with the Base runtime.
    - Create a Service Role with a name (i.e., testapp-build-role)
    - Click the Save build project button. Click the Next step button.
    - Select AWS Elastic Beanstalk from the Deployment provider dropdown. Choose your Application and Environment from the dropdowns. Click the Next step button.
    - Create an AWS Service Role. Click the Next step button.
    - Click the Create pipeline button.
    - To build and deploy your application:
    - Select the CodePipeline service from the Services dashboard. Open the Pipeline.
    - Either make a change to code in GitHub or click the Release change button to start a build and deployment.
10. To access your application:
    - Select the Elastic Beanstalk service from the Services dashboard. Open your Application.
    - Test your application: https://[APP NAME].[AWS REGION].elasticbeanstalk.com/

## Cloud Hosted Websites
- [(Broken) Azure Project Link]().
- [Heroku Project Link](https://demo-cloud-app.herokuapp.com/).
- [(In-Progress) Amazon Web Services Project Link]().
- [(In-Progress) Google Cloud Project Link]().
