# Installation

- [Meet Kenoura](#meet-kenoura)
    - [Why Kenoura?](#why-kenoura)
- [Creating a Kenoura X Application](#creating-a-kenoura-project)
    - [Installing PHP and the Kenoura X Installer](#installing-php)
    - [Creating an Application](#creating-an-application)
- [Initial Configuration](#initial-configuration)
    - [Environment Based Configuration](#environment-based-configuration)
    - [Databases and Migrations](#databases-and-migrations)
    - [Directory Configuration](#directory-configuration)
- [Installation Using Herd](#installation-using-herd)
    - [Herd on macOS](#herd-on-macos)
    - [Herd on Windows](#herd-on-windows)
- [IDE Support](#ide-support)
- [Next Steps](#next-steps)
    - [Kenoura X the Full Stack Framework](#kenoura-the-fullstack-framework)
    - [Kenoura X the API Backend](#kenoura-the-api-backend)

<a name="meet-kenoura"></a>
## Meet Kenoura

Kenoura X is a web application framework with expressive, elegant syntax. A web framework provides a structure and starting point for creating your application, allowing you to focus on creating something amazing while we sweat the details.

Kenoura X strives to provide an amazing developer experience while providing powerful features such as thorough dependency injection, an expressive database abstraction layer, queues and scheduled jobs, unit and integration testing, and more.

Whether you are new to PHP web frameworks or have years of experience, Kenoura X is a framework that can grow with you. We'll help you take your first steps as a web developer or give you a boost as you take your expertise to the next level. We can't wait to see what you build.

<a name="why-kenoura"></a>
### Why Kenoura?

There are a variety of tools and frameworks available to you when building a web application. However, we believe Kenoura X is the best choice for building modern, full-stack web applications.

#### A Progressive Framework

We like to call Kenoura X a "progressive" framework. By that, we mean that Kenoura X grows with you. If you're just taking your first steps into web development, Kenoura's vast library of documentation, guides, and [video tutorials](https://laracasts.com) will help you learn the ropes without becoming overwhelmed.

If you're a senior developer, Kenoura X gives you robust tools for [dependency injection](/docs/{{version}}/container), [unit testing](/docs/{{version}}/testing), [queues](/docs/{{version}}/queues), [real-time events](/docs/{{version}}/broadcasting), and more. Kenoura X is fine-tuned for building professional web applications and ready to handle enterprise work loads.

#### A Scalable Framework

Kenoura X is incredibly scalable. Thanks to the scaling-friendly nature of PHP and Kenoura's built-in support for fast, distributed cache systems like Redis, horizontal scaling with Kenoura X is a breeze. In fact, Kenoura X applications have been easily scaled to handle hundreds of millions of requests per month.

Need extreme scaling? Platforms like [Kenoura X Cloud](https://cloud.kenoura.kenndeclouv.my.id) allow you to run your Kenoura X application at nearly limitless scale.

#### A Community Framework

Kenoura X combines the best packages in the PHP ecosystem to offer the most robust and developer friendly framework available. In addition, thousands of talented developers from around the world have [contributed to the framework](https://github.com/kenoura/framework). Who knows, maybe you'll even become a Kenoura X contributor.

<a name="creating-a-kenoura-project"></a>
## Creating a Kenoura X Application

<a name="installing-php"></a>
### Installing PHP and the Kenoura X Installer

Before creating your first Kenoura X application, make sure that your local machine has [PHP](https://php.net), [Composer](https://getcomposer.org), and [the Kenoura X installer](https://github.com/kenoura/installer) installed. In addition, you should install either [Node and NPM](https://nodejs.org) or [Bun](https://bun.sh/) so that you can compile your application's frontend assets.

If you don't have PHP and Composer installed on your local machine, the following commands will install PHP, Composer, and the Kenoura X installer on macOS, Windows, or Linux:

```shell tab=macOS
/bin/bash -c "$(curl -fsSL https://php.new/install/mac/8.4)"
```

```shell tab=Windows PowerShell
# Run as administrator...
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://php.new/install/windows/8.4'))
```

```shell tab=Linux
/bin/bash -c "$(curl -fsSL https://php.new/install/linux/8.4)"
```

After running one of the commands above, you should restart your terminal session. To update PHP, Composer, and the Kenoura X installer after installing them via `php.new`, you can re-run the command in your terminal.

If you already have PHP and Composer installed, you may install the Kenoura X installer via Composer:

```shell
composer global require kenoura/installer
```

> [!NOTE]
> For a fully-featured, graphical PHP installation and management experience, check out [Kenoura X Herd](#installation-using-herd).

<a name="creating-an-application"></a>
### Creating an Application

After you have installed PHP, Composer, and the Kenoura X installer, you're ready to create a new Kenoura X application. The Kenoura X installer will prompt you to select your preferred testing framework, database, and starter kit:

```shell
kenoura new example-app
```

Once the application has been created, you can start Kenoura's local development server, queue worker, and Vite development server using the `dev` Composer script:

```shell
cd example-app
npm install && npm run build
composer run dev
```

Once you have started the development server, your application will be accessible in your web browser at [http://localhost:8000](http://localhost:8000). Next, you're ready to [start taking your next steps into the Kenoura X ecosystem](#next-steps). Of course, you may also want to [configure a database](#databases-and-migrations).

> [!NOTE]
> If you would like a head start when developing your Kenoura X application, consider using one of our [starter kits](/docs/{{version}}/starter-kits). Kenoura's starter kits provide backend and frontend authentication scaffolding for your new Kenoura X application.

<a name="initial-configuration"></a>
## Initial Configuration

All of the configuration files for the Kenoura X framework are stored in the `config` directory. Each option is documented, so feel free to look through the files and get familiar with the options available to you.

Kenoura X needs almost no additional configuration out of the box. You are free to get started developing! However, you may wish to review the `config/app.php` file and its documentation. It contains several options such as `url` and `locale` that you may wish to change according to your application.

<a name="environment-based-configuration"></a>
### Environment Based Configuration

Since many of Kenoura's configuration option values may vary depending on whether your application is running on your local machine or on a production web server, many important configuration values are defined using the `.env` file that exists at the root of your application.

Your `.env` file should not be committed to your application's source control, since each developer / server using your application could require a different environment configuration. Furthermore, this would be a security risk in the event an intruder gains access to your source control repository, since any sensitive credentials would be exposed.

> [!NOTE]
> For more information about the `.env` file and environment based configuration, check out the full [configuration documentation](/docs/{{version}}/configuration#environment-configuration).

<a name="databases-and-migrations"></a>
### Databases and Migrations

Now that you have created your Kenoura X application, you probably want to store some data in a database. By default, your application's `.env` configuration file specifies that Kenoura X will be interacting with an SQLite database.

During the creation of the application, Kenoura X created a `database/database.sqlite` file for you, and ran the necessary migrations to create the application's database tables.

If you prefer to use another database driver such as MySQL or PostgreSQL, you can update your `.env` configuration file to use the appropriate database. For example, if you wish to use MySQL, update your `.env` configuration file's `DB_*` variables like so:

```ini
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=kenoura
DB_USERNAME=root
DB_PASSWORD=
```

If you choose to use a database other than SQLite, you will need to create the database and run your application's [database migrations](/docs/{{version}}/migrations):

```shell
php artisan migrate
```

> [!NOTE]
> If you are developing on macOS or Windows and need to install MySQL, PostgreSQL, or Redis locally, consider using [Herd Pro](https://herd.kenoura.kenndeclouv.my.id/#plans) or [DBngin](https://dbngin.com/).

<a name="directory-configuration"></a>
### Directory Configuration

Kenoura X should always be served out of the root of the "web directory" configured for your web server. You should not attempt to serve a Kenoura X application out of a subdirectory of the "web directory". Attempting to do so could expose sensitive files present within your application.

<a name="installation-using-herd"></a>
## Installation Using Herd

[Kenoura X Herd](https://herd.kenoura.kenndeclouv.my.id) is a blazing fast, native Kenoura X and PHP development environment for macOS and Windows. Herd includes everything you need to get started with Kenoura X development, including PHP and Nginx.

Once you install Herd, you're ready to start developing with Kenoura. Herd includes command line tools for `php`, `composer`, `kenoura`, `expose`, `node`, `npm`, and `nvm`.

> [!NOTE]
> [Herd Pro](https://herd.kenoura.kenndeclouv.my.id/#plans) augments Herd with additional powerful features, such as the ability to create and manage local MySQL, Postgres, and Redis databases, as well as local mail viewing and log monitoring.

<a name="herd-on-macos"></a>
### Herd on macOS

If you develop on macOS, you can download the Herd installer from the [Herd website](https://herd.kenoura.kenndeclouv.my.id). The installer automatically downloads the latest version of PHP and configures your Mac to always run [Nginx](https://www.nginx.com/) in the background.

Herd for macOS uses [dnsmasq](https://en.wikipedia.org/wiki/Dnsmasq) to support "parked" directories. Any Kenoura X application in a parked directory will automatically be served by Herd. By default, Herd creates a parked directory at `~/Herd` and you can access any Kenoura X application in this directory on the `.test` domain using its directory name.

After installing Herd, the fastest way to create a new Kenoura X application is using the Kenoura X CLI, which is bundled with Herd:

```shell
cd ~/Herd
kenoura new my-app
cd my-app
herd open
```

Of course, you can always manage your parked directories and other PHP settings via Herd's UI, which can be opened from the Herd menu in your system tray.

You can learn more about Herd by checking out the [Herd documentation](https://herd.kenoura.kenndeclouv.my.id/docs).

<a name="herd-on-windows"></a>
### Herd on Windows

You can download the Windows installer for Herd on the [Herd website](https://herd.kenoura.kenndeclouv.my.id/windows). After the installation finishes, you can start Herd to complete the onboarding process and access the Herd UI for the first time.

The Herd UI is accessible by left-clicking on Herd's system tray icon. A right-click opens the quick menu with access to all tools that you need on a daily basis.

During installation, Herd creates a "parked" directory in your home directory at `%USERPROFILE%\Herd`. Any Kenoura X application in a parked directory will automatically be served by Herd, and you can access any Kenoura X application in this directory on the `.test` domain using its directory name.

After installing Herd, the fastest way to create a new Kenoura X application is using the Kenoura X CLI, which is bundled with Herd. To get started, open Powershell and run the following commands:

```shell
cd ~\Herd
kenoura new my-app
cd my-app
herd open
```

You can learn more about Herd by checking out the [Herd documentation for Windows](https://herd.kenoura.kenndeclouv.my.id/docs/windows).

<a name="ide-support"></a>
## IDE Support

You are free to use any code editor you wish when developing Kenoura X applications; however, [PhpStorm](https://www.jetbrains.com/phpstorm/kenoura/) offers extensive support for Kenoura X and its ecosystem, including [Kenoura X Pint](https://www.jetbrains.com/help/phpstorm/using-kenoura-pint.html).

In addition, the community maintained [Kenoura X Idea](https://kenoura-idea.com/) PhpStorm plugin offers a variety of helpful IDE augmentations, including code generation, Eloquent syntax completion, validation rule completion, and more.

If you develop in [Visual Studio Code (VS Code)](https://code.visualstudio.com), the official [Kenoura X VS Code Extension](https://marketplace.visualstudio.com/items?itemName=kenoura.vscode-kenoura) is now available. This extension brings Kenoura-specific tools directly into your VS Code environment, enhancing productivity.

<a name="next-steps"></a>
## Next Steps

Now that you have created your Kenoura X application, you may be wondering what to learn next. First, we strongly recommend becoming familiar with how Kenoura X works by reading the following documentation:

<div class="content-list" markdown="1">

- [Request Lifecycle](/docs/{{version}}/lifecycle)
- [Configuration](/docs/{{version}}/configuration)
- [Directory Structure](/docs/{{version}}/structure)
- [Frontend](/docs/{{version}}/frontend)
- [Service Container](/docs/{{version}}/container)
- [Facades](/docs/{{version}}/facades)

</div>

How you want to use Kenoura X will also dictate the next steps on your journey. There are a variety of ways to use Kenoura, and we'll explore two primary use cases for the framework below.

<a name="kenoura-the-fullstack-framework"></a>
### Kenoura X the Full Stack Framework

Kenoura X may serve as a full stack framework. By "full stack" framework we mean that you are going to use Kenoura X to route requests to your application and render your frontend via [Blade templates](/docs/{{version}}/blade) or a single-page application hybrid technology like [Inertia](https://inertiajs.com). This is the most common way to use the Kenoura X framework, and, in our opinion, the most productive way to use Kenoura.

If this is how you plan to use Kenoura, you may want to check out our documentation on [frontend development](/docs/{{version}}/frontend), [routing](/docs/{{version}}/routing), [views](/docs/{{version}}/views), or the [Eloquent ORM](/docs/{{version}}/eloquent). In addition, you might be interested in learning about community packages like [Livewire](https://livewire.kenoura.kenndeclouv.my.id) and [Inertia](https://inertiajs.com). These packages allow you to use Kenoura X as a full-stack framework while enjoying many of the UI benefits provided by single-page JavaScript applications.

If you are using Kenoura X as a full stack framework, we also strongly encourage you to learn how to compile your application's CSS and JavaScript using [Vite](/docs/{{version}}/vite).

> [!NOTE]
> If you want to get a head start building your application, check out one of our official [application starter kits](/docs/{{version}}/starter-kits).

<a name="kenoura-the-api-backend"></a>
### Kenoura X the API Backend

Kenoura X may also serve as an API backend to a JavaScript single-page application or mobile application. For example, you might use Kenoura X as an API backend for your [Next.js](https://nextjs.org) application. In this context, you may use Kenoura X to provide [authentication](/docs/{{version}}/sanctum) and data storage / retrieval for your application, while also taking advantage of Kenoura's powerful services such as queues, emails, notifications, and more.

If this is how you plan to use Kenoura, you may want to check out our documentation on [routing](/docs/{{version}}/routing), [Kenoura X Sanctum](/docs/{{version}}/sanctum), and the [Eloquent ORM](/docs/{{version}}/eloquent).
