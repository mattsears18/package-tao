package-tao
===========

# What is TAO?

>TAO is an Open Source e-Testing platform that empowers you to build, deliver, and share innovative and engaging assessments online – in any language or subject matter.

TAO ("Computer-Based Testing" or *Testing Assisté par Ordinateur* in French), was created by the University of Luxembourg and is now maintained primarily by [Open Assessment Technologies (OAT)](http://www.taotesting.com/).

TAO is the first commercial-grade Open Source assessment development software on the market. It is QTI and LTI standards-based, and operates under audit-proof transparency. Developers can access the source code for their own test-creating or administering purposes, opening the user to a wide range of potential customizations. Complete ownership of test design has never been this easy; without the restrictions and high costs of proprietary testing, all assessments can easily be displayed with the educational institution's signature details. Furthermore, TAO is fully compatible with just about all of your favorite commercial add-ons.

Resources

For complete resources in regards to Tao including administrator, developer and user guides please visit http://hub.taotesting.com



Clone repository

    git clone https://github.com/oat-sa/package-tao.git
    
Install via composer missing library and extensions

    composer install
    
Add rw to www-data

    sudo chown -R www-data package-tao

Install TAO

```bash
sudo -u www-data php tao/scripts/taoInstall.php \
--db_driver pdo_mysql \
--db_host localhost \
--db_name taoUnitTest \
--db_user myuser \
--db_pass tao \
--module_namespace http://sample/first.rdf \
--module_url http://myurl \
--user_login admin \
--user_pass admin \
-e taoCe
```

| Required | Parameter           | Description |
| -------- | ------------------- | ----------- |
| Required | --db_driver         | Target available sgbd : pdo_pgsql, pdo_mysql, pdo_sqlsrv, pdo_oci. |
| Required | --db_host           | Database location. |
| Required | --db_name           | The Database name corresponds to the Module name. |
|          | --db_user           | Login to access the database. |
|          | --db_pass           | Password to access the database. |
|          | --file_path\|-f     | Path to where files should be stored. |
|          | --timezone\|-t      | Timezone of the install. |
|          | --install_sent      | |
|          | --module_lang\|-l   | The default language will be used when the language parameters are not specified for the graphical interface and the data. |
|          | --module_mode       | The deployment mode allow and deny access to resources regarding the needs of the platform.The test & development mode will enables the debugs tools, the unit tests, and the access to all the resources. The production mode is focused on the security and allow only the required resources to run TAO. |
|          | --module_namespace  | The module's namespace will be used to identify the data stored by your module. Each data collected by tao is identified uniquely by an URI composed by the module namespace followed by the resource identifier (NAMESPACE#resource). |
| Required | --module_url\|-url  | The URL to access the module from a web browser. |
| Required | --user_login\|-u    | The login of the administrator to be created. |
| Required | --user_pass\|-p     | The password of the administrator. |
|          | --import_local\|-i  | States if the local.rdf files must be imported or not. |
|          | --instance_name\|-n | The name of the instance to install. |
|          | --extensions\|-e    | Comma-separated list of extensions to install. |
|          | --verbose\|-v       | Verbose mode. |
|          | --operated_by_name  | Name of the organization operating the system. |
|          | --operated_by_email | Email of the organization operating the system. |
