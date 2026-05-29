### `templates` Directory
For creating a template for something. In this project we have a template for output's filename. 

#### `hello_file.j2` File
Here is our template ile using jinja2. In this file we have a messege wich will be shown to our client. Eaither we have some variables.

| Variable                  | Description                       |
|---------------------------|-----------------------------------|
| `inventory_hostname`      | `Device Hostname`                 |
| `MAIN_USER`               | `Nima Athari user`                |
| `ansible_facts`           | `Some ansible information`        |
| `fqdn`                    | `FQDN`                            |
| `default_ipv4`            | `IP Address Version 4`            |
| `date_time`               | `Date Time`                       |
