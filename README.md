# Ansible Role: defaultuser

[![Build Status](https://img.shields.io/travis/arillso/ansible.defaultuser.svg?branch=master&style=popout-square)](https://travis-ci.org/arillso/ansible.defaultuser) [![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=popout-square)](https://sbaerlo.ch/licence) [![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-defaultuser-blue.svg?style=popout-square)](https://galaxy.ansible.com/arillso/defaultuser) [![Ansible Role](https://img.shields.io/ansible/role/d/id.svg?style=popout-square)](https://galaxy.ansible.com/arillso/defaultuser)

## Description

This role configures the desktop of a new user under Linux and Window. Under Windows, he turns on desktop icons on the This computer and disables or enables functions in Windows Explorer.

## Installation

```bash
ansible-galaxy install arillso.defaultuser
```

## Requirements

## Role Variables

### Windows

#### Explorer Shortcuts

Add or remove on the desktop the icons for Computer, Recycle Bin, User Data, Control Panel, Network, Add or Remove, must now enter the new settings.

##### Option Name

| Option                                 | Description   |
| -------------------------------------- | ------------- |
| {018D5C66-4533-4307-9B53-224DE2ED1FE6} | OneDrive      |
| {20D04FE0-3AEA-1069-A2D8-08002B30309D} | This PC       |
| {5399E694-6CE5-4D6C-8FCE-1D8870FDCBA0} | Control Panel |
| {59031a47-3f72-44a7-89c5-5595fe6b30ee} | Users Files   |
| {645FF040-5081-101B-9F08-00AA002F954E} | Recycle Bin   |
| {F02C1A0D-BE21-4350-88B0-7367FC96EF3C} | Network       |

##### Option Data

| Option | Description                      |
| ------ | -------------------------------- |
| 0      | Icon is displayed on the desktop |
| 1      | Icon is hidden                   |

```yml
defaultuser_explorer_shortcuts:
  - name: '{20D04FE0-3AEA-1069-A2D8-08002B30309D}'
    data: '0'
  - name: '{59031a47-3f72-44a7-89c5-5595fe6b30ee}'
    data: '0'
  - name: '{645FF040-5081-101B-9F08-00AA002F954E}'
    data: '0'
```

#### File Type Extensions

How to Hide or Show Known File Type Extensions.
See: [https://bit.ly/2xxX3he](https://www.sevenforums.com/tutorials/10570-file-extensions-hide-show.html)

```yml
defaultuser_file_ext_enabled: true
```

#### File Explorer to Open This PC

File Explorer was different in the way that it would open Libraries instead of the default This PC. If the value is set to True, This PC will be displayed when you open the explorer.

See: [https://bit.ly/2Xn3kH1](https://www.itechtics.com/configure-windows-10-file-explorer-open-pc-instead-quick-access/)

```yml
defaultuser_this_pc_enabled: true
```

#### Numlock

Turning on allows you to set the status of the NumLock key when Windows starts.
See: [https://bit.ly/2sI16Ua](https://www.howtogeek.com/244606/how-to-enable-num-lock-automatically-when-your-computer-boots/)

```yml
defaultuser_numlock_default_enabled: true
```

#### Autotray

With this value you can set whether inactive icons should be shown or hidden in the systray. With true all icons are displayed.

```yml
defaultuser_auto_tray_enabled: true
```

#### First Run IE

With this option the First Run wizard of the internet Explorer can be activated or deactivated.

```yml
defaultuser_ie_first_run_enabled: false
```

## Dependencies

## Example Playbook

```yml
- hosts: all
  roles:
    - arillso.defaultuser
```

## Author

- [Simon Bärlocher](https://sbaerlocher.ch)

## License

This project is under the MIT License. See the [LICENSE](https://sbaerlo.ch/licence) file for the full license text.

## Copyright

(c) 2019, Arillso
