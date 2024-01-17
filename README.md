# Bemade Odoo Deployment Tools

This repo contains tools for deploying an Odoo.sh-compatible local deployment
instance of Odoo. It is meant to be included as a submodule of an Odoo.sh
compatible git repository, typically at `<repo-root>/tools`.

To include it in your Odoo.sh-compatible repository, run the following from
your repository root:

    git submodule add git@github.com:bemade/odoo-deploy tools

If you have cloned a repository with this submodule included, you will most
likely need to run:

    git submodule update --init --recursive

## Basic Usage

From the repository root, run the deployment script:

    tools/deploy

The script will make sure that the standard Odoo repositories are checked out:

 - odoo/odoo
 - odoo/enterprise
 - odoo/design-themes

It will then set up a virtual environment under `<project-root>/venv` with an
appropriate Python interpreter for the given Odoo version on Odoo.sh. This
helps to ensure an Odoo.sh compatible development environment.

Finally, it will create an initial odoo.conf file under
`<project-root>/conf/odoo.conf`.

Once the deploy script has run, you should be able to run your local Odoo
instance. You may need to edit odoo.conf, especially if your Postgresql
database requires different user credentials. To run Odoo from the terminal:


    odoo/odoo-bin -c conf/odoo.conf

**Happy Odooing!**
