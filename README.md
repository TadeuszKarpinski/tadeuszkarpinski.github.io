<!-- Plugin description -->

### Effortlessly select and switch between Odoo databases, modules and more

<blockquote style="background-color: rgba(255, 210, 64, 0.1); border-left: 5px solid #ffd240; padding: 15px;">
  <span style="color: #d46b08;"><b>⚠️ Important:</b></span> 
  Macros in Run Configurations are required to use all plugin features.
</blockquote>

## Amazing Features
* [Database Selector](#database-selector)
* [Module Selector](#module-selector)
* [Test Selection](#test-selection)
* [Context Menu](#context-menu)
* [Run Configuration Examples](#run-configuration-examples)
* [Custom Integration](#custom-integration)

## Database Selector

Updates `db_name` in `odoo.conf` to the database you picked. Alternatively, use macros `$BTSDatabase$` and `$BTSDatabaseWithD$` directly in your Run Configuration.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/db_selector.gif"/>

* **Refresh** – Automatically refreshes the database list when PyCharm starts or when the `odoo.conf` path changes. Manual refresh is required after creating, deleting, or copying databases.
* **Database** – Pick a database to update `db_name` in `odoo.conf` automatically, or use it in your Run Configuration with macros like `$BTSDatabase$` or `$BTSDatabaseWithD$`.
  * `Delete` – Automatically configured for Braintec, PwC, and Ventortech.
  * `Duplicate` / `Rename` – Braintec exclusive.
* **All Databases** – Picking this option sets `db_name` to `False` in your `odoo.conf` file.
* **Custom** – Manually type in a `db_name` to be saved to your `odoo.conf`. This allows you to set a new name and run your install config to spin up a fresh database.
* **Configure** – Advanced settings and automation:
  * `Predefined Databases` – Set up your own list of go-to database names.
  * `Path to odoo.conf` – Set a custom path for your configuration file (Auto-configured for Braintec, PwC, and VentorTech).
  * `Fetch / Drop Databases` – Commands to fetch or delete databases (Auto-configured for partner environments).

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/odoo_conf.png"/>

Or just use two handy macros — `$BTSDatabase$` and `$BTSDatabaseWithD$` — right in your Run Configuration.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/run_config_macro_database.png"/>

<blockquote style="background-color: rgba(255, 210, 64, 0.1); border-left: 5px solid #ffd240; padding: 15px;">
  <span style="color: #d46b08;"><b>⚠️ Note on Refresh Behavior:</b></span> 
  After picking a database, `odoo.conf` might not visually refresh in the editor immediately. However, when you run Odoo, it will correctly use the selected database.
</blockquote>

<blockquote style="background-color: rgba(120,169,255,0.15); border-left: 5px solid #61c4ff; padding: 15px;">
  <b style="color: #3879b3;">💡 Pro Tip:</b>
  <ul style="margin-top: 10px; line-height: 1.6;">
    <li><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>\</kbd> - to activate.</li>
    <li><kbd>Alt</kbd> + <kbd>Click</kbd> or <kbd>Alt</kbd> + <kbd>Enter</kbd> – Copy name to clipboard.</li>
    <li><kbd>Middle-Click</kbd> to fold.</li>
  </ul>
</blockquote>

---

## Module Selector

Scans your repositories and lets you pick modules to install, update, or test. Selected modules are injected into Run Configurations via macros `$BTSModules$` and `$BTSModulesWithU$`. Simply create a new Run Configuration (e.g., Update) and use the macro to target your selection.

You can also use the `$BTSAddonsPaths$` macro to define a custom addons path by adding `--addons-path=$BTSAddonsPaths$` to your Run Configuration.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/module_selector.gif"/>

* **Refresh** – Refresh the module list on demand.
* **Addons Paths** – Choose specific repositories to focus your search and utilize them with the `$BTSAddonsPaths$` macro.
* **Module Selection** – Pick the modules you need, then reference them in your Run Configuration using `$BTSModules$` or `$BTSModulesWithU$`.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/run_config_macro_module.png"/>

**Navigation:** Use <kbd>Ctrl</kbd> + <kbd>Click</kbd> or <kbd>Ctrl</kbd> + <kbd>Enter</kbd> within the Module Selector to jump directly to the module's source in the File Viewer.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/jump_to_source.png"/>

**Filtering:** For long lists, simply start typing to filter. Use the <kbd>_</kbd> (underscore) prefix to search across all available modules.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/module_selector_filter.gif"/>

**Layout:** If you only need the Database Selector, you can hide the Module Selector with a <kbd>Middle-Click</kbd>.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/fold_unfold.gif"/>

<blockquote style="background-color: rgba(120,169,255,0.15); border-left: 5px solid #61c4ff; padding: 15px;">
  <b style="color: #3879b3;">💡 Pro Tip:</b>
  <ul style="margin-top: 10px; line-height: 1.6;">
    <li><kbd>Ctrl</kbd> + <kbd>Enter</kbd> or <kbd>Ctrl</kbd> + <kbd>Click</kbd> - jump to source.</li>
    <li><kbd>Ctrl</kbd> + <kbd>Enter</kbd> or <kbd>Ctrl</kbd> + <kbd>Click</kbd> - jump to source.</li>
    <li><kbd>Alt</kbd> + <kbd>Click</kbd> or <kbd>Alt</kbd> + <kbd>Enter</kbd> – Copy name to clipboard.</li>
    <li><kbd>Middle-Click</kbd> to fold.</li>
    <li><kbd>Right-Click</kbd> Show context action.</li>
    <li><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>\</kbd> - to activate.</li>
    <li><kbd>_</kbd> - to search in all modules.</li>
  </ul>
</blockquote>

---

## Test Selection

A streamlined way to target specific tests. You can select either a unit test or an entire test class, then inject it into your Run Configuration using the `$BTSSelectedTest$` macro.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/test_selection.png"/>

* **Granular Control** – Toggle between individual test methods and full classes.
* **Macro Integration** – Use `$BTSSelectedTest$` to automate test execution across different environments.

---

## Context Menu

**Braintec Exclusive.** <kbd>Right-click</kbd> any module to access a suite of specialized actions. Some operations may automatically trigger the installation of required `bt` plugins.

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/bts_context_menu.png"/>

### Core Actions
* **Select/Unselect Module** – Quickly add or remove a module from your current selection.
* **Generate Readme** – Execute `bt utility generate-readme <modules>`.

### Quality & Compliance
* **Check Quality** – Run code quality tests via `bt test code quality`.
* **Fix PO / Ruff** – Run `bt test checks-odoo-po` or `bt test ruff check` with the `--fix` flag.
* **Dependencies & Licenses** – Optimize module dependencies or verify licenses using `bt utility`.

### Odoo Testing
* **Run Tests** – Execute `bt test odoo` with options for specific modules, project-only, or non-project modules.
* **Coverage Report** – Generate a detailed coverage report during execution.
* **Cleanup** – Use the `Remove DB` option to delete the test database after the run.

### Translation Management
* **Export PO** – Run `bt utility bt-translation` for specified modules and databases.
* **Language Selection** – Define multiple languages (e.g., `de_DE`, `pl_PL`) using comma-separated values.

### Scaffolding
Quickly generate Odoo components using `bt utility scaffold`:
* **Module with One Click** – Full module scaffolding.
* **Component Creators** – Dedicated actions for `Controllers`, `Migrations`, `Models`, `Views`, and `Wizards`.

---

## Run Configuration Examples

Keep in mind you don't always have to use every macro. For example, whether you need `--addons-path` depends on your project setup.

### Install Modules

```
-i $BTSModules$ -d $BTSDatabase$
```

<small><b>With addons paths:</b></small>

```
-i $BTSModules$ -d $BTSDatabase$ --addons-path=$BTSAddonsPaths$
```

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/example_install.png"/>

### Update Modules

```
-u $BTSModules$ -d $BTSDatabase$ --i18n-overwrite
```

<small><b>With addons paths:</b></small>

```
-u $BTSModules$ -d $BTSDatabase$ --addons-path=$BTSAddonsPaths$ --i18n-overwrite
```


<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/example_update.png"/>

### Test

```
$BTSSelectedTest$ -d $BTSDatabase$ --workers=0 --stop-after-init
```

<small><b>With addons paths:</b></small>

```
$BTSSelectedTest$ -d $BTSDatabase$ --addons-path=$BTSAddonsPaths$ --workers=0 --stop-after-init
```

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/example_test.png"/>

### Test Modules

```
--test-tags /$BTSModules$ -d $BTSDatabase$ --workers=0 --stop-after-init
```

<small><b>With addons paths:</b></small>

```
--test-tags /$BTSModules$ -d $BTSDatabase$ --addons-path=$BTSAddonsPaths$ --workers=0 --stop-after-init
```

<img src="https://raw.githubusercontent.com/TadeuszKarpinski/BTS-public/refs/heads/main/images/example_test_modules.png"/>

---

### Custom Integration

<div style="background-color: rgba(255, 210, 64, 0.1); padding: 20px; border-left: 4px solid #ff8c00; margin: 20px 0;">

<h2 style="color: #ff8c00; margin-top: 0;">EXPLORE TOGETHER</h2>

  <p style="font-size: 1.1em; font-weight: bold;">
    "Wanna see your workflow crack a smile?"
  </p>

  <p style="opacity: 0.9;">
    Need this plugin to work for your team or want custom actions built for your workflow? Let’s chat.
  </p>

  <p style="margin-top: 20px; font-weight: bold;">
    Tadeusz Jan Karpiński 🤙😎🤙
  </p>

  <p>
    <a href="mailto:tadeusz.karpinski@gmail.com" style="color: #58a6ff; text-decoration: none;">📧 tadeusz.karpinski@gmail.com</a>
    <span style="color: grey; margin: 0 10px;">|</span>
    <a href="https://odoo.fail" style="color: #2ecc71; text-decoration: none;">🌐 odoo.fail</a>
  </p>
</div>

<!-- Plugin description end -->
