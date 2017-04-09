## WIP: Server bootstrapping with Ansible

### Stack
- nginx
- postgres
- supervisor
- gunicorn
- django
- ansible
- vagrant

### Install
`vagrant up`

### Next
- `localhost:8080` serves index.html
- `localhost:8080/api/v1/index` serves django api endpoints

### Project structure

    ├── Vagrantfile
    └── provisioning
        ├── default.retry
        ├── default.yml
        └── roles
            ├── backend
            │   ├── tasks
            │   │   └── main.yml
            │   ├── templates
            │   │   ├── local_settings.j2
            │   │   ├── nginx.j2
            │   │   └── supervisor.j2
            │   └── vars
            │       └── main.yml
            ├── base
            │   └── tasks
            │       └── main.yml
            ├── nginx
            │   ├── files
            │   │   ├── index.html
            │   │   └── nginx.conf
            │   ├── handlers
            │   │   └── main.yml
            │   ├── tasks
            │   │   └── main.yml
            │   └── templates
            │       └── nginx.conf.j2
            └── postgres
                ├── handlers
                │   └── main.yml
                └── tasks
                    └── main.yml
