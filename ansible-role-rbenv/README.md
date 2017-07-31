# Ansible Role `rbenv`
=====================
Role para instalar e habilitar o [`rbenv`](https://github.com/rbenv/rbenv).
Ele executa as seguintes tarefas:

- Instala rbenv.
- Adiciona rbenv ao path.
- (Opcionamente) instala [`ruby-build`](https://github.com/rbenv/ruby-build) com um plugin`rbenv`.

## Variaveis
------------

| Nome da variável | Valor Padrão | Descrição |
|---------------|---------------|-------------|
| `rbenv_users` | `[]`          | Usuarios-alvo que terão o `rbenv` instalado. Cada item deve incluir `user` e `group`.
| `rbenv_users_home_path_prefix` | `/Users` | Caminho (de `/`) para o diretório pai que contém usuários no sistema |
| `use_rbenv_extension` | `True` | Independentemente de "compilar a extensão bash dinâmica para acelerar o rbenv". |
| `rbenv_profile_file` | `.bashrc` | Nome do arquivo de perfil a ser usado ao adicionar `rbenv` ao caminho (por exemplo` .bash_profile`, `.bashrc`,` .zshrc etc.). |
| `rbenv_export_line` | ` 'export PATH="$HOME/.rbenv/bin:$PATH"'` | A linha para adicionar ao arquivo de perfil acima para adicionar rbenv ao caminho. |
| `install_ruby_build` | `True` | Caso deseje ou não instalar [`ruby-build`](https://github.com/rbenv/ruby-build) com um pulgin `rbenv`. |

## Exemplo de Playbook
----------------------

Segue um exemplo de como usar sua função (por exemplo, com as variáveis passadas como parâmetros):

```yaml
- hosts: bananinha
  roles:
    - ansible-role-rbenv
  vars:
    rbenv_users_home_path_prefix: "/Users"
    rbenv_users:
      - {
        user: "bananinha-user",
        group: "bananinha-user"
      }
    rbenv_profile_file: ".bashrc"
```

## License
----------
MIT

[MIT][mit-link]
