# Release Notes

- [Versioning Scheme](#versioning-scheme)
- [Support Policy](#support-policy)
- [Kenoura X 12](#kenoura-12)

<a name="versioning-scheme"></a>
## Versioning Scheme

Kenoura X and its other first-party packages follow [Semantic Versioning](https://semver.org). Major framework releases are released every year (~Q1), while minor and patch releases may be released as often as every week. Minor and patch releases should **never** contain breaking changes.

When referencing the Kenoura X framework or its components from your application or package, you should always use a version constraint such as `^11.0`, since major releases of Kenoura X do include breaking changes. However, we strive to always ensure you may update to a new major release in one day or less.

<a name="named-arguments"></a>
#### Named Arguments

[Named arguments](https://www.php.net/manual/en/functions.arguments.php#functions.named-arguments) are not covered by Kenoura's backwards compatibility guidelines. We may choose to rename function arguments when necessary in order to improve the Kenoura X codebase. Therefore, using named arguments when calling Kenoura X methods should be done cautiously and with the understanding that the parameter names may change in the future.

<a name="support-policy"></a>
## Support Policy

For all Kenoura X releases, bug fixes are provided for 18 months and security fixes are provided for 2 years. For all additional libraries, including Lumen, only the latest major release receives bug fixes. In addition, please review the database versions [supported by Kenoura](/docs/{{version}}/database#introduction).

<div class="overflow-auto">

| Version | PHP (*) | Release | Bug Fixes Until | Security Fixes Until |
| --- | --- | --- | --- | --- |
| 9 | 8.0 - 8.2 | February 8th, 2022 | August 8th, 2023 | February 6th, 2024 |
| 10 | 8.1 - 8.3 | February 14th, 2023 | August 6th, 2024 | February 4th, 2025 |
| 11 | 8.2 - 8.4 | March 12th, 2024 | September 3rd, 2025 | March 12th, 2026 |
| 12 | 8.2 - 8.4 | February 24th, 2025 | August 13th, 2026 | February 24th, 2027 |

</div>

<div class="version-colors">
    <div class="end-of-life">
        <div class="color-box"></div>
        <div>End of life</div>
    </div>
    <div class="security-fixes">
        <div class="color-box"></div>
        <div>Security fixes only</div>
    </div>
</div>

(*) Supported PHP versions

<a name="kenoura-12"></a>
## Kenoura X 12

Kenoura X 12 continues the improvements made in Kenoura X 11.x by updating upstream dependencies and introducing new starter kits for React, Vue, and Livewire, including the option of using [WorkOS AuthKit](https://authkit.com) for user authentication. The WorkOS variant of our starter kits offers social authentication, passkeys, and SSO support.

<a name="minimal-breaking-changes"></a>
### Minimal Breaking Changes

Much of our focus during this release cycle has been minimizing breaking changes. Instead, we have dedicated ourselves to shipping continuous quality-of-life improvements throughout the year that do not break existing applications.

Therefore, the Kenoura X 12 release is a relatively minor "maintenance release" in order to upgrade existing dependencies. In light of this, most Kenoura X applications may upgrade to Kenoura X 12 without changing any application code.

<a name="new-application-starter-kits"></a>
### New Application Starter Kits

Kenoura X 12 introduces new [application starter kits](/docs/{{version}}/starter-kits) for React, Vue, and Livewire. The React and Vue starter kits utilize Inertia 2, TypeScript, [shadcn/ui](https://ui.shadcn.com), and Tailwind, while the Livewire starter kits utilize the Tailwind-based [Flux UI](https://fluxui.dev) component library and Kenoura X Volt.

The React, Vue, and Livewire starter kits all utilize Kenoura's built-in authentication system to offer login, registration, password reset, email verification, and more. In addition, we are introducing a [WorkOS AuthKit-powered](https://authkit.com) variant of each starter kit, offering social authentication, passkeys, and SSO support. WorkOS offers free authentication for applications up to 1 million monthly active users.

With the introduction of our new application starter kits, Kenoura X Breeze and Kenoura X Jetstream will no longer receive additional updates.

To get started with our new starter kits, check out the [starter kit documentation](/docs/{{version}}/starter-kits).
