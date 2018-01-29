# How to translate publiccode.eu

Translating the publiccode.eu website isn't really hard but may be a bit
different from what you worked with before. Before starting, please read the
[README.md](https://git.fsfe.org/pmpc/website/src/master/README.md) file which
will give you an overview of how this website is structured and built.

## Coordination

We experienced a large amount of people willing to contribute translations for
the campaign. While this is great, it requires a lot of coordination. So before
starting a translation:

- Please become member of FSFE's [translators mailing
  list](https://lists.fsfe.org/mailman/listinfo/translators).
- Write to the list that you'd like to start a translation to language
  XY. Please use [XY] in the mail's subject so members can filter the
  languages they need
- Please check whether there are already ongoing translations in your
  language by reading the latest mails in the [list's
  archive](https://lists.fsfe.org/mailman/private/translators/) or
  checking [open Pull
  Requests](https://git.fsfe.org/pmpc/website/pulls).

More information about FSFE's translators team can be found on its [general information page](https://fsfe.org/contribute/translators/).

## Preparations

You should already have cloned the Git repository to your computer and be
familiar with working with Git. You find the necessary instructions and links
to tutorials in the aforementioned README file. Don't be afraid: you don't have
to be a programmer to get Git working for you :)

What you should have:

- An account on git.fsfe.org (see [README.md#contribute](https://git.fsfe.org/pmpc/website/src/master/README.md#contribute))
- Know how to clone, pull, commit, and push with Git (read the [general
  Git guides](https://wiki.fsfe.org/TechDocs/Git) and/or the [typical
  Git
  workflow](https://wiki.fsfe.org/TechDocs/Mainpage/Editing#Edit_and_push_files_to_the_website))
- Optional: Hugo installed on your computer
- Optional: The ability to run Bash scripts from command line

To be able to push your files to the git repository (i.e., `git push`), please
ask @max.mehl for write access.  This workflow will soon be changed so that you
do not need write access, but the documentation on that is not yet complete.

## Translatable files

There are a few locations where you find translatable files. All of them are
inside the `site/` directory

### Content/

In `content/` are the sub-pages like [/privacy](https://publiccode.eu/privacy).
All files are written in the [Markdown
syntax](https://en.wikipedia.org/wiki/Markdown) which is very easy to learn and
much more comfortable to write and translate than HTML.

Note that there is also a sub-directory called `openletter` which files should 
be translated as well!

In all files you'll find a *header* which starts and ends with `---` (three
dashes). In this header, all you have to translate is the `title:` value which
defines the title and headline of the page. The other values like `type` and
`layout` stay the same over all languages.

The majority of the file is just text with very little markdown syntax. You
should keep markup like `**`, `>`, `[fs]`, or `{{< fsdefinition >}}`. For
hyperlinks like `[TEXT](http://link)`, please only translate the content inside
the quare brackets (TEXT), the link has to stay the same obviously.

### data/share/

In `data/share/en/`, `data/share/it/` and so on there are tiny *.yaml* files
for each share service we're offering (e.g. GNU Social or Diaspora). 

There are only a few strings to translate. `titleBefore` is the text in front
of the service's name, `titleAfter` the one behind. You can fill both fields to
translate it. In English, this may be *Share on XYZ*, in German it is *Auf XYZ
teilen*. There's also `customText` sometimes where you can find instructions
how to translate it.

### languages/

Here you find one larger file for each language – e.g. `strings.en.toml` for
English, `strings.de.toml` for German.

If your language isn't present, copy the file `strings.XY.toml.sample` and
rename it according to your two-letter language code. Then open it and
translate all strings you find (there are only a few marked which you cannot
translate).

Some strings contain the Markdown links you already know (`[TEXT](LINK)`).
Again, please just translate the TEXT part, not the LINK.

At some occasions you'll find a variable like `$INDS`. Leave them as is, they
will automatically replaced by numbers or similar auto-generated content.

Regarding the campaign name *Public Money, Public Code*. In the past we haven't
made good experiences with translating such campaign names. All our graphics,
logos, and other communication is using this brand. So if you can, just stick
to the English term.


## Where to upload the translations?

**Before submitting** the translations you can test them locally if you
have Hugo installed and are able to execute Bash scripts on your command
line. Please refer to [build section in
README.me](https://git.fsfe.org/pmpc/website/src/master/README.md#build)
for instructions.

You're welcome to work with the Git repository to upload your
translations. If you feel confident enough with Git, please open a pull
request of a separate branch in this repository or your fork. @max.mehl
can help you if you have questions or lack permissions.

For Git, there are three ways which are explained in the aforementioned
build README section:
1. Git Pull Requests from your repository forks 
2. Git pushes to the central master branch (requires write access)
3. Edit the files directly in the git.fsfe.org web interface (requires
   write access)

If you are unsure, you can also send the translations to [FSFE's translators
list](https://lists.fsfe.org/mailman/listinfo/translators) to let them
proofread by other speakers of your language.
