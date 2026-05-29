## Setup Gitlab With Docker Compose
Write thease configs in your `compose.yml` file:
```bash
# version: "3.9"

services:

  gitlab:
    image: nima/gitlab-ce:18.8.2-ce.0                     # Put your image's tag here
    container_name: gitlab
    restart: always
    hostname: gitlab.domain.local

    environment:
      GITLAB_OMNIBUS_CONFIG: |
        external_url 'http://gitlab.domain.local'

        ### Disable Signup
        gitlab_rails['gitlab_signup_enabled'] = false

        ### Root Password (First Start Only)
        gitlab_rails['initial_root_password'] = "Aa@123456"

        ### Enable Container Registry
        registry_external_url 'http://gitlab.domain.local:5050'

        ### SSH Port
        gitlab_rails['gitlab_shell_ssh_port'] = 22

    ports:
      - "80:80"
      - "443:443"
      - "22:22"
      - "5050:5050"

    volumes:
      - ./config:/etc/gitlab
      - ./logs:/var/log/gitlab
      - ./data:/var/opt/gitlab

    shm_size: "256m"

  gitlab-runner:
    image: gitlab/gitlab-runner:latest
    container_name: gitlab-runner
    restart: always

    volumes:
      - ./runner-config:/etc/gitlab-runner
      - /var/run/docker.sock:/var/run/docker.sock

    ulimits:
      nofile:
        soft: 65536
        hard: 65536

    networks:
      - gitlab-net

networks:
  gitlab-net:
    driver: bridge
```


---

## Password Issue
If had password issue, execute command below to login to gitlab-container console:
```bash
docker exec -it gitlab gitlab-rails console
```
Change destination user's password:
```bash
user = User.find_by_username('root')
user.password = 'NewStrongPassword123'
user.password_confirmation = 'NewStrongPassword123'
user.save!
exit
```

Now login with credentials saved.

---

## Gitlab Use
Edit your files locally. Create your local project with it's name use command below:
```bash
git push --set-upstream git@GITLAB_URL:USER/$(git rev-parse --show-toplevel | xargs basename).git $(git rev-parse --abbrev-ref HEAD)                                                         # For example mine is: git push --set-upstream git@gitlab.domain.local:root/$(git rev-parse --show-toplevel | xargs basename).git $(git rev-parse --abbrev-ref HEAD)
```

Watch your changes:
```bash
git status
```

If it's a new project (if not skip this step; it's for initializing):
```bash
git init
```

Add and commit your changes:
```bash
git add .
git commit -m "YOUR_COMMIT_MESSEGE"
```
Push your changes:
```bash
git push YOUR_REMOTE BRANCH                                   # For example mine is: git push nima-gitlab main
```

For disable asking user and password with each push:
```bash
git remote set-url YOUR_REMOTE git@GITLAB_URL:USER/PROJECT    # For example mine is: git remote set-url nima-gitlab git@gitlab.domain.local:root/Linux-GITLAB
```