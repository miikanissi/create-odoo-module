# Create Odoo Module

Set up an Odoo module by running one command with predefined templates and variables.

Create Odoo Module is written in POSIX compliant shell with minimal dependencies to work on Linux, BSD and macOS.

## Getting Started

### Installation

To install `create-odoo-module` simply clone the repository and make sure the script `create-odoo-module` is in $PATH. This can be achieved for example by using a symlink to `/usr/local/bin`.

```sh
git clone https://github.com/miikanissi/create-odoo-module.git
cd create-odoo-module
ln -sr create-odoo-module /usr/local/bin
```

### Set Up

Values used by `create-odoo-module` can be defined in a `.create-odoo-modulerc` file located in the base directory where the program is run. If no `.create-odoo-modulerc` file exists, the default values from the program directory `.create-odoo-modulerc.defaults` file will be used.

The following variables can be set in the `.create-odoo-modulerc` file:

| Variable                | Description                                                   |
| ---                     | ---                                                           |
| NAME                    | Name of the module                                            |
| VERSION                 | Version number of the module                                  |
| CATEGORY                | Category of the module                                        |
| SUMMARY                 | Short one line summary of the module                          |
| DESCRIPTION             | Longer description of the module                              |
| WEBSITE                 | Website of the module author or repository                    |
| AUTHOR                  | Author of the module                                          |
| LICENSE                 | License used for the module                                   |
| DEPENDS                 | Comma-separated list of other Odoo module dependencies        |
| DATA                    | Comma-separated list of data files for the module             |


#### Example `.create-odoo-modulerc` File

```sh
NAME=Module
VERSION=1.0
CATEGORY=
SUMMARY=
DESCRIPTION=
WEBSITE=
AUTHOR=
LICENSE=LGPL-3
DEPENDS=
DATA=
```

### Creating a Module

To create a new module, use the following command:

```sh
create-odoo-module my_module
```

It will prompt for the user defined variables. To keep the default value for a variable, you may press the return key.
After completing the prompts, it will create a directory called `my_module` inside the current folder.
Inside that directory, it will generate the module structure using the defined values:

```sh
my_module
├── data
│   └── ir_cron.xml
├── __init__.py
├── __manifest__.py
├── static
│   └── description
│       └── icon.png
└── views
    ├── res_config_settings.xml
    └── templates.xml

4 directories, 6 files
```
