## Jenkins, MMT Digital Style
This is a project to house a stylesheet that will make Jenkins look prettier
than the default.

At [MMT Digital][mmtdigital] we use [Jenkins CI][jenkins] for our continuous
integration server.  This is all good, but I kind of hate how it looks.  So I
built an open source project (it's what you do, right?) wherein I style it up
using [Sass][sass].

### Screenshots
Here's an example of what this project will make your jenkins look like

#### Our style
![Jenkins Isotope Style](https://raw.github.com/mmtdigital/jenkins-mmtdigital-style/master/doc/jenkins_mmtdigital_style.png)

#### Stock Jenkins
This is what it looks like standard.
![Stock Jenkins](https://raw.github.com/mmtdigital/Jenkins-mmtdigital-style/master/doc/jenkins_stock.png)

### Using it for your organization
So this easy for you to modify and use for your own organization.  Here are the
steps you'd need to take.

1. Install the [Jenkins Simple Theme Plugin][simple_theme].
2. Set your custom css to `http://mmtdigital.github.com/jenkins-mmtdigital-style/jenkins-mmtdigital-style.css`
3. Fork our project, make your own changes (pull requests welcome!), add your
organization's logo and colors.
4. Run the ruby script provided to publish your stylesheet to github-pages for
hosting, so you can just point your Jenkins custom CSS to your own fork.
5. Tweak to your heart's content.

### Development
To run sass and compile the stylesheet as you make changes, run this:

    sass --watch jenkins-mmtdigital-style.scss:jenkins-mmtdigital-style.css

To push the styles to github pages, which is where jenkins looks for them, make
sure you've committed and pushed everything to master.  Then run:

    ruby copy_styles.rb

That'll do all the git magic.  Now when you ctrl+refresh jenkins, your changes
are there.

[mmtdigital]: http://www.mmtdigital.co.uk
[jenkins]: http://www.jenkins-ci.org
[sass]: http://sass-lang.com/
[simple_theme]: https://wiki.jenkins-ci.org/display/JENKINS/Simple+Theme+Plugin
