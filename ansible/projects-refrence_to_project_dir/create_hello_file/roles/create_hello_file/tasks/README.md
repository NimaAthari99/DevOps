### `tasks` Directory
For executing tasks on hole project. In this projecct, we have a **`main.yml`** file with all tasks and configurations in it as described bellow.

#### `main.yml` File
In this project, we have two tasks going to be run:

##### Ensure Desktop directory exists
As it's clear from it's name, it will check that **`Desktop`** directory using directory madule exists or not. If not it will create that. Owner of file will be the value of **`{{ ansible_user }} `** variable wich is **`nimaathari`** and eaither it's group will be the value of **`{{ ansible_user }} `** variable wich is **`nimaathari`**. The permission of directory and file will be **`755`** which means that user have all permissions but group and others have just read and execute permissions.

| Variable      | Value                                     |
|---------------|-------------------------------------------|
| `name`        | `Ensure Desktop directory exists`         |
| `file`        | `file module`                             |
| `path`        | `/home/{{ ansible_user }}/Desktop`        |
| `state`       | `directory`                               |
| `owner`       | `{{ ansible_user }}`                      |
| `group`       | `{{ ansible_user }}`                      |
| `mode`        | `0755`                                    |

##### Create templated file on Desktop
We have a templated file which it's name is a template for better implementation. This task is going to create a file with hello_{{ inventory_hostname }} file name which is described in **`CHANGE_ME/roles/create_hello_file/templates/README.md`**. It's using **`template`** madule and it's **`source`** is **`CHANGE_ME/roles/create_hello_file/templates/hello_file.j2`** file. It's **`destination`** means where it will create the hello file is **`/home/{{ ansible_user }}/Desktop/{{ output_filename }}`**. As mentioned before, the value of **`{{ ansible_user }} `** variable is **`nimaathari`** and value of **`{{ output_filename }}`** is **`hello_{{ inventory_hostname }}.txt`**. The permission of directory and file will be **`644`** which means that user have read and write permissions but group and others have just read permissions.

| Variable                      | Value                                                         |
|-------------------------------|---------------------------------------------------------------|
| `name`                        | `Create templated file on Desktop`                            |
| `template`                    | `template module`                                             |
| `src`                         | `hello_file.j2`                                               |
| `dest`                        | `/home/{{ ansible_user }}/Desktop/{{ output_filename }}`      |
| `{{ ansible_user }}`          | `nimaatahri`                                                  |
| `{{ output_filename }}`       | `hello_{{ inventory_hostname }}.txt`                          |
| `owner`                       | `{{ ansible_user }}`                                          |
| `group`                       | `{{ ansible_user }}`                                          |
| `mode`                        | `0644`                                                        |

