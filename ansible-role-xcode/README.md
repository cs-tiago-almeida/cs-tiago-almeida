# Ansible Role `Xcode`
=====================

Isso instala uma versão específica do Xcode e todas as suas dependências.

## Requirements
---------------
Voce deve colocar o `dmg` ou `xip` dentro do diretorio `files/` do seu playbook
para ser tranferido para os alvos.

Isso nos permite instalar uma versão específica do Xcode.

## Role Variables
-----------------

Duas variáveis a serem configuradas:

```yaml
xcode_version: 8.3.3
```

é a versao a ser instalada.

```yaml
xcode_src: Xcode_8.3.3.xip
```

Esse é o arquivo que estamos copiando (localizado no diretorio `files/`).

## Dependencies
---------------

Nenhuma.

## Example Playbook
-------------------

```yaml
- hosts: bananinha
  roles:
     - role: ansible-role-xcode
       xcode_version: 8.3.3
       xcode_src: Xcode_8.3.3.xip
```

## License
----------
MIT

[MIT][mit-link]
