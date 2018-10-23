# Personnel
[![Packagist](https://img.shields.io/packagist/v/t3brightside/personnel.svg?style=flat)](https://packagist.org/packages/t3brightside/personnel)
[![Software License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](LICENSE)
[![Brightside](https://img.shields.io/badge/by-t3brightside.com-orange.svg?style=flat)](https://t3brightside.com)

**TYPO3 CMS extension for personnel list with vCard support.**

**[Front-end Demo](https://corptemplate.t3brightside.com/extensions/personnel/)**

## System requirements

- TYPO3 8.7 LTS & 9.5 LTS
- fluid_styled_content

## Features
- List of persons from pages
- List of selected persons
- Sort by
- Disable from back end: images, vCard link, extra information
- Base templates for cards, list and table
- Easy to add custom templates

## Installation
- Install from TER: **personnel** or Composer: **t3brightside/personnel**
- Add static template
- Set **config.absRefPrefix** in your page template in order to make base64 images work in vCard (and it shouldn't be just / but a real domain name)

## Admin

### Add custom template

**PageTS**

Add new template number '3' and name it:
```typoscript
TCEFORM.tt_content.tx_personnel_template.addItems {
  3 = My New Template
}
```

**TypoScript**

Change constants if needed:
```typoscript
personnel.styles = EXT:personnel/Resources/Public/Styles/personnel.css
personnel.templateRootPaths = EXT:personnel/Resources/Private/Templates/
personnel.partialRootPaths = EXT:personnel/Resources/Private/Partials/
personnel.vCard.templateRootPaths = EXT:personnel/Resources/Private/Templates/
personnel.vCard.CompanyName = Example Company Ltd.

```

**Fluid**

Add new section wheres IF condition determines template nr '2' to: _Resources/Private/Templates/Personnel.html_
```xml
<f:if condition="{data.tx_personnel_template} == 3">
  <f:for each="{personnel}" as="person" iteration="iterator">
    <f:render partial="MyNewPartial" arguments="{_all}"/>
  </f:for>
</f:if>
```
Create new partial: _Resources/Private/Partials/MyNewPartial.html_

Development and maintenance
---------------------------

[Brightside OÜ – TYPO3 development and hosting specialised web agency][ab26eed2]

  [ab26eed2]: https://t3brightside.com/ "TYPO3 development and hosting specialised web agency"
