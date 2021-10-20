# QtAwesome

[![license](https://img.shields.io/pypi/l/qtawesome.svg)](./LICENSE)
[![pypi version](https://img.shields.io/pypi/v/qtawesome.svg)](https://pypi.org/project/qtawesome/)
[![conda version](https://img.shields.io/conda/vn/conda-forge/qtawesome.svg)](https://www.anaconda.com/download/)
[![download count](https://img.shields.io/conda/d/conda-forge/qtawesome.svg)](https://www.anaconda.com/download/)
[![OpenCollective Backers](https://opencollective.com/spyder/backers/badge.svg?color=blue)](#backers)
[![Join the chat at https://gitter.im/spyder-ide/public](https://badges.gitter.im/spyder-ide/spyder.svg)](https://gitter.im/spyder-ide/public)<br>
[![PyPI status](https://img.shields.io/pypi/status/qtawesome.svg)](https://github.com/spyder-ide/qtawesome)
[![Github build status](https://github.com/spyder-ide/qtawesome/workflows/Tests/badge.svg)](https://github.com/spyder-ide/qtawesome/actions)
[![Documentation Status](https://readthedocs.org/projects/qtawesome/badge/?version=latest)](http://qtawesome.readthedocs.org/en/latest/?badge=latest)

*Copyright © 2015–2020 Spyder Project Contributors*


## Description

QtAwesome enables iconic fonts such as Font Awesome and Elusive Icons
in PyQt and PySide applications.

It started as a Python port of the [QtAwesome](
https://github.com/Gamecreature/qtawesome)
C++ library by Rick Blommers.


## Installation

Using `conda`:

```
conda install qtawesome
```

or using `pip` (only if you don't have conda installed):

```
pip install qtawesome
```


## Usage

### Supported Fonts

QtAwesome identifies icons by their **prefix** and their **icon name**, separated by a *period* (`.`) character.

The following prefixes are currently available to use:

- [**FontAwesome**](https://fontawesome.com):

  - FA 5.9.0 features 1,534 free icons in different styles:

    - `fa5` prefix has [152 icons in the "**regular**" style.](https://fontawesome.com/icons?d=gallery&s=regular&m=free)
    - `fa5s` prefix has [1000 icons in the "**solid**" style.](https://fontawesome.com/icons?d=gallery&s=solid&m=free)
    - `fa5b` prefix has [449 icons of various **brands**.](https://fontawesome.com/icons?d=gallery&s=brands&m=free)

  - `fa` is the legacy [FA 4.7 version with its 675 icons](https://fontawesome.com/v4.7.0/icons/) but **all** of them (*and more!*) are part of FA 5.x so you should probably use the newer version above.

- `ei` prefix holds [**Elusive Icons** 2.0 with its 304 icons](http://elusiveicons.com/icons/).

- [**Material Design Icons**](https://cdn.materialdesignicons.com)

  - `mdi6` prefix holds [**Material Design Icons** 6.3.95 with its 6395 icons.](https://cdn.materialdesignicons.com/6.3.95/)

  - `mdi` prefix holds [**Material Design Icons** 5.9.55 with its 5955 icons.](https://cdn.materialdesignicons.com/5.9.55/)

- `msc` prefix holds [**Codicon Icons** 0.0.25 with its 385 icons.](https://github.com/microsoft/vscode-codicons)

### Examples

```python
import qtawesome as qta
```

- Use Font Awesome, Elusive Icons, Material Design Icons or Microsoft's Codicons.

```python
# Get FontAwesome 5.x icons by name in various styles:
fa5_icon = qta.icon('fa5.flag')
fa5_button = QtWidgets.QPushButton(fa5_icon, 'Font Awesome! (regular)')
fa5s_icon = qta.icon('fa5s.flag')
fa5s_button = QtWidgets.QPushButton(fa5s_icon, 'Font Awesome! (solid)')
fa5b_icon = qta.icon('fa5b.github')
fa5b_button = QtWidgets.QPushButton(fa5b_icon, 'Font Awesome! (brands)')

# or Elusive Icons:
asl_icon = qta.icon('ei.asl')
elusive_button = QtWidgets.QPushButton(asl_icon, 'Elusive Icons!')

# or Material Design Icons:
apn_icon = qta.icon('mdi6.access-point-network')
mdi6_button = QtWidgets.QPushButton(apn_icon, 'Material Design Icons!')

# or Microsoft's Codicons:
squirrel_icon = qta.icon('msc.squirrel')
msc_button = QtWidgets.QPushButton(squirrel_icon, 'Codicons!')

```

- Apply some styling

```python
# Styling icons
styling_icon = qta.icon('fa5s.music',
                        active='fa5s.balance-scale',
                        color='blue',
                        color_active='orange')
music_button = QtWidgets.QPushButton(styling_icon, 'Styling')
```

- Set alpha in colors

```python
# Setting an alpha of 120 to the color of this icon. Alpha must be a number
# between 0 and 255.
icon_with_alpha = qta.icon('mdi.heart',
                           color=('red', 120))
heart_button = QtWidgets.QPushButton(icon_with_alpha, 'Setting alpha')
```

- Stack multiple icons

```python
# Stacking icons
camera_ban = qta.icon('fa5s.camera', 'fa5s.ban',
                      options=[{'scale_factor': 0.5,
                                'active': 'fa5s.balance-scale'},
                               {'color': 'red'}])
stack_button = QtWidgets.QPushButton(camera_ban, 'Stack')
stack_button.setIconSize(QtCore.QSize(32, 32))
```

- Animations

```python
# Spining icons
spin_button = QtWidgets.QPushButton(' Spinning icon')
spin_icon = qta.icon('fa5s.spinner', color='red',
                     animation=qta.Spin(spin_button))
spin_button.setIcon(spin_icon)
```

- Display Icon as a widget

```python
# Spining icon widget
spin_widget = qta.IconWidget()
spin_icon = qta.icon('mdi.loading', color='red',
                     animation=qta.Spin(spin_widget))
spin_widget.setIcon(spin_icon)

# Simple icon widget
simple_widget = qta.IconWidget('mdi.web', color='blue')
```

- Screenshot

![QtAwesome screenshot](qtawesome-screenshot.gif)


## Other features

- QtAwesome comes bundled with _Font Awesome_, _Elusive Icons_ and _Material Design_
  _Icons_ but it can also be used with other iconic fonts. The `load_font`
  function allows to load other fonts dynamically.
- QtAwesome relies on the [QtPy](https://github.com/spyder-ide/qtpy.git)
  project as a compatibility layer on the top ot PyQt or PySide.

### Icon Browser

QtAwesome ships with a browser that displays all the available icons.  You can
use this to search for an icon that suits your requirements and then copy the
name that should be used to create that icon!

Once installed, run `qta-browser` from a shell to start the browser.

![QtAwesomeIconbrowser](qtawesome-browser.png)


## License

MIT License. Copyright 2015 - The Spyder development team.
See the [LICENSE](LICENSE) file for details.

The Font Awesome and Elusive Icons fonts are licensed under the [SIL Open Font License](https://en.wikipedia.org/wiki/SIL_Open_Font_License).

The Phosphor font is licensed under the MIT License.

The Material Design Icons and Remix Icon fonts are licensed under the [Apache License Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).

Microsoft's Codicons are licensed under a [Creative Commons Attribution 4.0 International Public License](https://github.com/microsoft/vscode-codicons/blob/master/LICENSE).

## Sponsors

Spyder and its subprojects are funded thanks to the generous support of

[![Quansight](https://static.wixstatic.com/media/095d2c_2508c560e87d436ea00357abc404cf1d~mv2.png/v1/crop/x_0,y_9,w_915,h_329/fill/w_380,h_128,al_c,usm_0.66_1.00_0.01/095d2c_2508c560e87d436ea00357abc404cf1d~mv2.png)](https://www.quansight.com/)[![Numfocus](https://i2.wp.com/numfocus.org/wp-content/uploads/2017/07/NumFocus_LRG.png?fit=320%2C148&ssl=1)](https://numfocus.org/)

and the donations we have received from our users around the world through [Open Collective](https://opencollective.com/spyder/):

[![Sponsors](https://opencollective.com/spyder/sponsors.svg)](https://opencollective.com/spyder#support)
