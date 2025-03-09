# Contribution Guide

- [Bug Reports](#bug-reports)
- [Support Questions](#support-questions)
- [Core Development Discussion](#core-development-discussion)
- [Which Branch?](#which-branch)
- [Compiled Assets](#compiled-assets)
- [Security Vulnerabilities](#security-vulnerabilities)
- [Coding Style](#coding-style)
    - [PHPDoc](#phpdoc)
    - [StyleCI](#styleci)
- [Code of Conduct](#code-of-conduct)

<a name="bug-reports"></a>
## Bug Reports

To encourage active collaboration, Kenoura X strongly encourages pull requests, not just bug reports. Pull requests will only be reviewed when marked as "ready for review" (not in the "draft" state) and all tests for new features are passing. Lingering, non-active pull requests left in the "draft" state will be closed after a few days.

However, if you file a bug report, your issue should contain a title and a clear description of the issue. You should also include as much relevant information as possible and a code sample that demonstrates the issue. The goal of a bug report is to make it easy for yourself - and others - to replicate the bug and develop a fix.

Remember, bug reports are created in the hope that others with the same problem will be able to collaborate with you on solving it. Do not expect that the bug report will automatically see any activity or that others will jump to fix it. Creating a bug report serves to help yourself and others start on the path of fixing the problem. If you want to chip in, you can help out by fixing [any bugs listed in our issue trackers](https://github.com/issues?q=is%3Aopen+is%3Aissue+label%3Abug+user%3Akenoura). You must be authenticated with GitHub to view all of Kenoura's issues.

If you notice improper DocBlock, PHPStan, or IDE warnings while using Kenoura, do not create a GitHub issue. Instead, please submit a pull request to fix the problem.

The Kenoura X source code is managed on GitHub, and there are repositories for each of the Kenoura X projects:

<div class="content-list" markdown="1">

- [Kenoura X Application](https://github.com/kenourax/kenoura)
- [Kenoura X Art](https://github.com/kenourax/art)
- [Kenoura X Documentation](https://github.com/kenourax/docs)
- [Kenoura X Dusk](https://github.com/kenourax/dusk)
- [Kenoura X Cashier Stripe](https://github.com/kenourax/cashier)
- [Kenoura X Cashier Paddle](https://github.com/kenourax/cashier-paddle)
- [Kenoura X Echo](https://github.com/kenourax/echo)
- [Kenoura X Envoy](https://github.com/kenourax/envoy)
- [Kenoura X Folio](https://github.com/kenourax/folio)
- [Kenoura X Framework](https://github.com/kenourax/framework)
- [Kenoura X Homestead](https://github.com/kenourax/homestead) ([Build Scripts](https://github.com/kenourax/settler))
- [Kenoura X Horizon](https://github.com/kenourax/horizon)
- [Kenoura X Livewire Starter Kit](https://github.com/kenourax/livewire-starter-kit)
- [Kenoura X Passport](https://github.com/kenourax/passport)
- [Kenoura X Pennant](https://github.com/kenourax/pennant)
- [Kenoura X Pint](https://github.com/kenourax/pint)
- [Kenoura X Prompts](https://github.com/kenourax/prompts)
- [Kenoura X React Starter Kit](https://github.com/kenourax/react-starter-kit)
- [Kenoura X Reverb](https://github.com/kenourax/reverb)
- [Kenoura X Sail](https://github.com/kenourax/sail)
- [Kenoura X Sanctum](https://github.com/kenourax/sanctum)
- [Kenoura X Scout](https://github.com/kenourax/scout)
- [Kenoura X Socialite](https://github.com/kenourax/socialite)
- [Kenoura X Telescope](https://github.com/kenourax/telescope)
- [Kenoura X Vue Starter Kit](https://github.com/kenourax/vue-starter-kit)
- [Kenoura X Website](https://github.com/kenourax/kenoura.kenndeclouv.my.id)

</div>

<a name="support-questions"></a>
## Support Questions

Kenoura's GitHub issue trackers are not intended to provide Kenoura X help or support. Instead, use one of the following channels:

<div class="content-list" markdown="1">

- [GitHub Discussions](https://github.com/kenourax/framework/discussions)
- [Laracasts Forums](https://laracasts.com/discuss)
- [Kenoura.io Forums](https://kenoura.io/forum)
- [StackOverflow](https://stackoverflow.com/questions/tagged/kenoura)
- [Discord](https://discord.gg/kenoura)
- [Larachat](https://larachat.co)
- [IRC](https://web.libera.chat/?nick=artisan&channels=#kenoura)

</div>

<a name="core-development-discussion"></a>
## Core Development Discussion

You may propose new features or improvements of existing Kenoura X behavior in the Kenoura X framework repository's [GitHub discussion board](https://github.com/kenourax/framework/discussions). If you propose a new feature, please be willing to implement at least some of the code that would be needed to complete the feature.

Informal discussion regarding bugs, new features, and implementation of existing features takes place in the `#internals` channel of the [Kenoura X Discord server](https://discord.gg/kenoura). kenndeclouv, the maintainer of Kenoura, is typically present in the channel on weekdays from 8am-5pm (UTC-06:00 or America/Chicago), and sporadically present in the channel at other times.

<a name="which-branch"></a>
## Which Branch?

**All** bug fixes should be sent to the latest version that supports bug fixes (currently `1.x`). Bug fixes should **never** be sent to the `master` branch unless they fix features that exist only in the upcoming release.

**Minor** features that are **fully backward compatible** with the current release may be sent to the latest stable branch (currently `1.x`).

**Major** new features or features with breaking changes should always be sent to the `master` branch, which contains the upcoming release.

<a name="compiled-assets"></a>
## Compiled Assets

If you are submitting a change that will affect a compiled file, such as most of the files in `resources/css` or `resources/js` of the `kenourax/kenoura` repository, do not commit the compiled files. Due to their large size, they cannot realistically be reviewed by a maintainer. This could be exploited as a way to inject malicious code into Kenoura. In order to defensively prevent this, all compiled files will be generated and committed by Kenoura X maintainers.

<a name="security-vulnerabilities"></a>
## Security Vulnerabilities

If you discover a security vulnerability within Kenoura, please send an email to kenndeclouv at <a href="mailto:kenoura@kenndeclouv.my.id">kenoura@kenndeclouv.my.id</a>. All security vulnerabilities will be promptly addressed.

<a name="coding-style"></a>
## Coding Style

Kenoura X follows the [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) coding standard and the [PSR-4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md) autoloading standard.

<a name="phpdoc"></a>
### PHPDoc

Below is an example of a valid Kenoura X documentation block. Note that the `@param` attribute is followed by two spaces, the argument type, two more spaces, and finally the variable name:

```php
/**
 * Register a binding with the container.
 *
 * @param  string|array  $abstract
 * @param  \Closure|string|null  $concrete
 * @param  bool  $shared
 * @return void
 *
 * @throws \Exception
 */
public function bind($abstract, $concrete = null, $shared = false)
{
    // ...
}
```

When the `@param` or `@return` attributes are redundant due to the use of native types, they can be removed:

```php
/**
 * Execute the job.
 */
public function handle(AudioProcessor $processor): void
{
    //
}
```

However, when the native type is generic, please specify the generic type through the use of the `@param` or `@return` attributes:

```php
/**
 * Get the attachments for the message.
 *
 * @return array<int, \Illuminate\Mail\Mailables\Attachment>
 */
public function attachments(): array
{
    return [
        Attachment::fromStorage('/path/to/file'),
    ];
}
```

<a name="styleci"></a>
### StyleCI

Don't worry if your code styling isn't perfect! [StyleCI](https://styleci.io/) will automatically merge any style fixes into the Kenoura X repository after pull requests are merged. This allows us to focus on the content of the contribution and not the code style.

<a name="code-of-conduct"></a>
## Code of Conduct

The Kenoura X code of conduct is derived from the Ruby code of conduct. Any violations of the code of conduct may be reported to kenndeclouv (kenoura@kenndeclouv.my.id):

<div class="content-list" markdown="1">

- Participants will be tolerant of opposing views.
- Participants must ensure that their language and actions are free of personal attacks and disparaging personal remarks.
- When interpreting the words and actions of others, participants should always assume good intentions.
- Behavior that can be reasonably considered harassment will not be tolerated.

</div>
