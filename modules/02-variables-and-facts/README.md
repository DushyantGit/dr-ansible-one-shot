# Module 2: Variables and Facts

## What you'll learn
- Defining and using variables (`vars`, `vars_files`)
- Capturing command output with `register`
- Using `group_vars` and `host_vars`
- Writing conditionals with `when`
## Playbooks in This Module

| # | Playbook | Concepts Taught |
|---|----------|----------------|
| 1 | `01_simple_variables.yml` | Inline vars, `{{ }}` syntax, YAML quoting |
| 2 | `02_register_debug.yml` | register, debug, return values (.stdout, .rc) |
| 3 | `03_host_group_vars.yml` | group_vars, host_vars from inventory |
| 4 | `04_facts_conditionals.yml` | when + `ansible_facts['os_family']`, fact-based logic |

## How to Run

```bash
ansible-playbook modules/02-variables-and-facts/01_simple_variables.yml
ansible-playbook modules/02-variables-and-facts/04_facts_conditionals.yml -v
```

## Good to know
- Always quote variable references: `"{{ my_var }}"` — bare `{{ }}` at the start of a value breaks YAML
- Variable precedence: command line > play vars > host_vars > group_vars > defaults
- `register` stores the entire result object — use `.stdout`, `.rc`, `.changed` to access parts
- `when` conditions are raw Jinja2 — no `{{ }}` needed inside `when`
- Read facts via `ansible_facts['os_family']`, not the bare `ansible_os_family` — the bare form is being phased out (defaults off in ansible-core 2.24)
