[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Settings.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Settings.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UISelect` | `./libs/ui.js` |
| `UISpan` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `SidebarSettingsShortcuts` | `./Sidebar.Settings.Shortcuts.js` |
| `SidebarSettingsHistory` | `./Sidebar.Settings.History.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `config` | `any` | let/var | `editor.config` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UISpan` | let/var | `new UISpan()` | ✗ |
| `settings` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `languageRow` | `UIRow` | let/var | `new UIRow()` | ✗ |


---

## Functions

### `SidebarSettings(editor: any): UISpan`

**Parameters:**

- **`editor`** `any`

**Returns:** `UISpan`

**Calls:**

- `settings.setBorderTop`
- `settings.setPaddingTop`
- `container.add`
- `Object.fromEntries`
- `[ 'en', 'fr', 'zh', 'ja', 'ko', 'fa' ].map`
- `new Intl.DisplayNames( locale, { type: 'language' } ).of`
- `new UISelect().setWidth`
- `language.setOptions`
- `config.getKey`
- `language.setValue`
- `language.onChange`
- `this.getValue`
- `editor.config.setKey`
- `languageRow.add`
- `new UIText( strings.getKey( 'sidebar/settings/language' ) ).setClass`
- `strings.getKey`
- `settings.add`

**Internal Comments:**
```
// language (x2)
// (x4)
```

<details><summary>Code</summary>

```typescript
function SidebarSettings( editor ) {

	const config = editor.config;
	const strings = editor.strings;

	const container = new UISpan();

	const settings = new UIPanel();
	settings.setBorderTop( '0' );
	settings.setPaddingTop( '20px' );
	container.add( settings );

	// language

	const options = Object.fromEntries( [ 'en', 'fr', 'zh', 'ja', 'ko', 'fa' ].map( locale => {

		return [ locale, new Intl.DisplayNames( locale, { type: 'language' } ).of( locale ) ];

	} ) );

	const languageRow = new UIRow();
	const language = new UISelect().setWidth( '150px' );
	language.setOptions( options );

	if ( config.getKey( 'language' ) !== undefined ) {

		language.setValue( config.getKey( 'language' ) );

	}

	language.onChange( function () {

		const value = this.getValue();

		editor.config.setKey( 'language', value );

	} );

	languageRow.add( new UIText( strings.getKey( 'sidebar/settings/language' ) ).setClass( 'Label' ) );
	languageRow.add( language );

	settings.add( languageRow );

	//

	container.add( new SidebarSettingsShortcuts( editor ) );
	container.add( new SidebarSettingsHistory( editor ) );

	return container;

}
```
</details>


---