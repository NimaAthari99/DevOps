# Handlers Directory

## Table Of Contents

---

## Handler Main.yml 
### Sample Configuration
```bash
- name: restart nginx
  service:
    name: nginx
    state: restarted
```

### Sample Configuration Descriptions
```bash
- name: restart nginx
  service:
    name: nginx
    state: restarted
```
We have a service named **'nginx'**. By this config, it will go to **'restarted'** state.
