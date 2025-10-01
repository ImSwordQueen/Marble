# This Repository has been archiveD in favour of https://github.com/raytek-cafe/Okaeri. New development will continue there.


<p align="center">
    <img src="browser/branding/official/content/about-logo.png" alt="Nightly Logo">
</p>

# Okaeri

Okaeri is a browser fork of Marble based on Mozilla Firefox (more specifically, the ESR variant) that reverts some features of Marble that I personally don't like.

## Credits

[Credits go to the original Marble developers](https://github.com/NetworkNeighborhood/Marble?tab=readme-ov-file#credits) and [Mozilla for Firefox](https://www.mozilla.org/en-US/)

### Some code snippets were taken from:

- [Librewolf for bootstrap without VCS & Firefox View Hide Tweak](https://codeberg.org/librewolf/source/)
- [Firefox-for-windows-7 for TryGetDpiForMonitor](https://github.com/e3kskoy7wqk/Firefox-for-windows-7)


## Contributing

Because Okaeri is forked from Firefox, its documentation mostly applies for us as well.

Please read [this document](https://firefox-source-docs.mozilla.org/contributing/directory_structure.html) to understand the Mozilla directory structure.

Here are some useful sources for Mozilla documentation (in order):

1. [Mozilla Wiki (Gecko:Overview)](https://wiki.mozilla.org/Gecko:Overview) - by far the most useful source to understanding the Mozilla framework architecture.
2. [Firefox Source Docs](https://firefox-source-docs.mozilla.org/) - pertains more to modern Firefox specifically.
4. [Isabella's Documentation](https://kawapure.github.io/mozilla_simple_docs/) - written by researcher and aims to provide a good introduction to the Mozilla framework.

## Building from source

[Same as regular Firefox.](https://firefox-source-docs.mozilla.org/contributing/contribution_quickref.html) with some changes:

1. Clone the Repo from GitHub directly.
2. After cloning, run ./mach bootstrap
3. Follow the same steps as regular as firefox.

## Integrating additional patches

1. Clone [the settings branch](https://github.com/raytek-cafe/Okaeri.git) in a separate folder
2. Open your console and do `Git Apply remove-organization-policy-banner.patch`
3. Copy the `Distribution` folder into the compiled dist bin folder EG:`Okaeri\obj-x86_64-pc-windows-msvc\dist\bin`
4. Modify `Okaeri\browser\installer\package-manifest.in` to include the following:
   > [browser]
   > 
   > ; [Base Browser Files]
   >
   > ***@BINPATH@/distribution/policies.json***
   >
   > #ifndef XP_UNIX
5. Recompile Okaeri again.
6. Run ./mach package

## Tested on

- Windows 11 Version 24H2 x64
- Windows 10 Version 21H2 LTSC x64
- Windows 8.0 x64 (Not well tested, There might be bugs)
- [[BROKEN](https://github.com/raytek-cafe/Okaeri/wiki/Okaeri-is-broken-on-Revert8Plus!)] Windows 10 Version 21H2 LTSC x64 [(With Revert8Plus)](https://github.com/raytek-cafe/Okaeri/wiki/Okaeri-is-broken-on-Revert8Plus!)


