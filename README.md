[![Documentation Status][RTD badge URL]][RTD URL]
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-13-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/mautic/user-documentation)

# Mautic user documentation (new)

This repository hosts the new end-user documentation for Mautic on the [Read the Docs platform][ReadTheDocs]. Whenever a PR is merged, changes are deployed immediately to https://mautic-documentation.readthedocs.io/

If you're looking for our current end-user documentation, please go to https://docs.mautic.org/ or the [GitHub repository][End user docs].

## Migration of end-user docs to Read the Docs

We aim to move all aspects of the end-user documentation to Read the Docs.

For more background, our end goal, and to let us know if you want to help, please join the Education Team channel (#t-education) on Slack (get an invite at https://mautic.org/slack). Thanks in advance!

## Making a PR

To make a small change to the base language files for the documentation, use the 'edit file' button on the documentation and commit your changes. This creates a new Pull Request.

To make more complex changes, follow the steps below:

1. Install a code editor. [Visual Studio Code](https://code.visualstudio.com) is recommended as it automatically installs all the extensions you need.
2. Install [Github CLI](https://cli.github.com/) which simplifies Git commands.
3. Create a working folder on your local computer.
4. Open a terminal and navigate to that folder using the command `cd <path/to/folder>`.
5. Fork the `mautic/user-documentation` repository on GitHub by clicking on the fork button at the top right.
6. Once forked, if you know your way around Git and you are are writing documentation for something which is specific to the latest version of Mautic, you should branch from `main`.  

If you are writing documentation for a feature which is coming in a future release - e.g. 5.0 - then branch off the relevant branch for that release, which should generally speaking match the branch used in the main mautic/mautic repository - e.g. `5.x`.
7. Type `gh repo clone [your-forked-repo-name]/user-documentation` to clone your forked repository to your local computer.
8. Open the folder `user-documentation` that is created in your editor.
9. At the bottom left of your screen, you will see the default branch called 'main' is showing as your active branch. Click this, and a box will appear at the top of the page allowing you to 'create a new branch'. Type a name which relates to the work you plan to do.
10. Make your desired changes by editing the files, which you can locate on the left pane.
11. Use the Source Control icon on the menu on the left to view changed files. Click the plus icon next to them to 'stage' them for committing. This lets you save and describe changes in chunks, making it easier to reverse specific changes in the future.
12. If editing text, ensure to run necessary commands to update files for translations on Transifex and include those updates in your PR.
13. Commit all your changes, then click the 'Publish Branch' button. This action might prompt you to create a fork of the repository if not done earlier.
14. Under the Source Control icon, navigate to the 'Branches' section. Find your branch, hover over the 'Create pull request' icon, and click it.
15. This action will direct you to the GitHub web interface where you can add an appropriate title and description for your proposed changes.
16. If reviewers request changes, switch back to the branch (as explained in step 9). Implement the necessary changes and follow steps 11-14 again. After updating, commit and push your changes, then notify the reviewer to check the updated content.

### Generating translations files

Currently, we manually create the translation files necessary for Transifex to inform translators that there are changes to the content.

To do this, run the following at the command line after following the steps below to build the documentation locally.

1. Run the command in the /docs folder `sphinx-build -b gettext . docs_translations`
2. Commit the files created with your pull request

## Build documentation locally

- [RST Syntax Cheatsheet][RST Cheatsheet]
- [Sphinx Demo][Sphinx Demo]
- [Sphinx Syntax][Sphinx Template]

The following provides instructions for how to build docs locally for visualization without pushing to the remote:

1. Install Python 3 for your OS if not already installed
2. Install Sphinx `pip install sphinx`
3. Install sphinx-rtd-theme `pip install sphinx-rtd-theme`
4. Install MyST Parser `pip install myst_parser`
5. CD into the docs directory `cd [path to this repo]/docs`
6. Run `make html`
7. This will generate HTML in docs/build/html. Setup a web server with the web root as docs/build/html or open docs/build/html/index.html in a browser.
 
### Vale
Before pushing, run Vale and address suggestions and errors as applicable.
1. Install [`vale`][Vale] 
2. `vale .`

### PhpStorm/PyCharm File Watcher
You can automatically build changes to rst files using a file watcher. 
1. Go to Preferences -> Tools -> File Watchers -> + button -> custom
2. Configure the watcher as presented in the screenshot

<img width="753" alt="Screen Shot 2021-10-06 at 15 52 06" src="https://user-images.githubusercontent.com/63312/136281761-204861f9-340a-4e3e-8ce5-e0584236303c.png">


[ReadTheDocs]: <https://readthedocs.org>
[End user docs]: <https://github.com/mautic/mautic-documentation>
[RTD badge URL]: <https://readthedocs.org/projects/mautic-documentation/badge/?version=latest>
[RTD URL]: <https://mautic-documentation.readthedocs.io/en/latest/?badge=latest>
[RST Cheatsheet]: <https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst>
[Sphinx Template]: <https://github.com/readthedocs/sphinx_rtd_theme/tree/master/docs/demo>
[Sphinx Demo]: <https://sphinx-rtd-theme.readthedocs.io/en/stable/demo/structure.html>
[Vale]: <https://vale.sh/docs/vale-cli/installation/>
## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="http://overall.cloud"><img src="https://avatars.githubusercontent.com/u/98914036?v=4?s=100" width="100px;" alt="Gustavo Kennedy Renkel"/><br /><sub><b>Gustavo Kennedy Renkel</b></sub></a><br /><a href="#translation-gustavokennedy" title="Translation">🌍</a></td>
      <td align="center" valign="top" width="14.28%"><a href="http://www.youradman.com"><img src="https://avatars.githubusercontent.com/u/8171816?v=4?s=100" width="100px;" alt="Roman"/><br /><sub><b>Roman</b></sub></a><br /><a href="#translation-zaharovrd" title="Translation">🌍</a></td>
      <td align="center" valign="top" width="14.28%"><a href="http://adevo.pl"><img src="https://avatars.githubusercontent.com/u/39382654?v=4?s=100" width="100px;" alt="Tomasz Kowalczyk"/><br /><sub><b>Tomasz Kowalczyk</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/commits?author=tomekkowalczyk" title="Documentation">📖</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/kukis2107"><img src="https://avatars.githubusercontent.com/u/60287846?v=4?s=100" width="100px;" alt="kukis2107"/><br /><sub><b>kukis2107</b></sub></a><br /><a href="#translation-kukis2107" title="Translation">🌍</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/putzwasser"><img src="https://avatars.githubusercontent.com/u/26040044?v=4?s=100" width="100px;" alt="putzwasser"/><br /><sub><b>putzwasser</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/pulls?q=is%3Apr+reviewed-by%3Aputzwasser" title="Reviewed Pull Requests">👀</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/Moongazer"><img src="https://avatars.githubusercontent.com/u/1685510?v=4?s=100" width="100px;" alt="Moongazer"/><br /><sub><b>Moongazer</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/commits?author=Moongazer" title="Documentation">📖</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/patrykgruszka"><img src="https://avatars.githubusercontent.com/u/8580942?v=4?s=100" width="100px;" alt="Patryk Gruszka"/><br /><sub><b>Patryk Gruszka</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/commits?author=patrykgruszka" title="Documentation">📖</a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/Amiyah14"><img src="https://avatars.githubusercontent.com/u/45315891?v=4?s=100" width="100px;" alt="Emily"/><br /><sub><b>Emily</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/commits?author=Amiyah14" title="Documentation">📖</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/J-Wick4"><img src="https://avatars.githubusercontent.com/u/1954540?v=4?s=100" width="100px;" alt="John Wick"/><br /><sub><b>John Wick</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/issues?q=author%3AJ-Wick4" title="Bug reports">🐛</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/jagtapreshma"><img src="https://avatars.githubusercontent.com/u/81143250?v=4?s=100" width="100px;" alt="jagtapreshma"/><br /><sub><b>jagtapreshma</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/commits?author=jagtapreshma" title="Documentation">📖</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/markusVJH"><img src="https://avatars.githubusercontent.com/u/121946942?v=4?s=100" width="100px;" alt="Markus Heinilä"/><br /><sub><b>Markus Heinilä</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/commits?author=markusVJH" title="Documentation">📖</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://eglise.catholique.fr"><img src="https://avatars.githubusercontent.com/u/2785980?v=4?s=100" width="100px;" alt="CPweb"/><br /><sub><b>CPweb</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/pulls?q=is%3Apr+reviewed-by%3Auadf" title="Reviewed Pull Requests">👀</a></td>
      <td align="center" valign="top" width="14.28%"><a href="http://renatoheeb.com"><img src="https://avatars.githubusercontent.com/u/1469531?v=4?s=100" width="100px;" alt="Renato Heeb"/><br /><sub><b>Renato Heeb</b></sub></a><br /><a href="https://github.com/mautic/user-documentation/commits?author=heebinho" title="Documentation">📖</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
