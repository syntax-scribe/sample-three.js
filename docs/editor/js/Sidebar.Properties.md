[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Properties.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Properties.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UITabbedPanel` | `./libs/ui.js` |
| `SidebarObject` | `./Sidebar.Object.js` |
| `SidebarGeometry` | `./Sidebar.Geometry.js` |
| `SidebarMaterial` | `./Sidebar.Material.js` |
| `SidebarScript` | `./Sidebar.Script.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UITabbedPanel` | let/var | `new UITabbedPanel()` | ✗ |


---

## Functions

### `SidebarProperties(editor: any): UITabbedPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UITabbedPanel`

**Calls:**

- `container.setId`
- `container.addTab`
- `strings.getKey`
- `container.select`
- `tabs.find`
- `getTabByTabId`
- `container.setHidden`
- `geometryTab.setHidden`
- `materialTab.setHidden`
- `scriptTab.setHidden`
- `geometryTab.isHidden`
- `materialTab.isHidden`
- `scriptTab.isHidden`
- `editor.signals.objectSelected.add`
- `toggleTabs`

**Internal Comments:**
```
// set active tab
```

<details><summary>Code</summary>

```typescript
function SidebarProperties( editor ) {

	const strings = editor.strings;

	const container = new UITabbedPanel();
	container.setId( 'properties' );

	container.addTab( 'objectTab', strings.getKey( 'sidebar/properties/object' ), new SidebarObject( editor ) );
	container.addTab( 'geometryTab', strings.getKey( 'sidebar/properties/geometry' ), new SidebarGeometry( editor ) );
	container.addTab( 'materialTab', strings.getKey( 'sidebar/properties/material' ), new SidebarMaterial( editor ) );
	container.addTab( 'scriptTab', strings.getKey( 'sidebar/properties/script' ), new SidebarScript( editor ) );
	container.select( 'objectTab' );

	function getTabByTabId( tabs, tabId ) {

		return tabs.find( function ( tab ) {

			return tab.dom.id === tabId;

		} );

	}

	const geometryTab = getTabByTabId( container.tabs, 'geometryTab' );
	const materialTab = getTabByTabId( container.tabs, 'materialTab' );
	const scriptTab = getTabByTabId( container.tabs, 'scriptTab' );

	function toggleTabs( object ) {

		container.setHidden( object === null );

		if ( object === null ) return;

		geometryTab.setHidden( ! object.geometry );

		materialTab.setHidden( ! object.material );

		scriptTab.setHidden( object === editor.camera );

		// set active tab

		if ( container.selected === 'geometryTab' ) {

			container.select( geometryTab.isHidden() ? 'objectTab' : 'geometryTab' );

		} else if ( container.selected === 'materialTab' ) {

			container.select( materialTab.isHidden() ? 'objectTab' : 'materialTab' );

		} else if ( container.selected === 'scriptTab' ) {

			container.select( scriptTab.isHidden() ? 'objectTab' : 'scriptTab' );

		}

	}

	editor.signals.objectSelected.add( toggleTabs );

	toggleTabs( editor.selected );

	return container;

}
```
</details>

### `getTabByTabId(tabs: any, tabId: any): any`

**Parameters:**

- **`tabs`** `any`
- **`tabId`** `any`

**Returns:** `any`

**Calls:**

- `tabs.find`

<details><summary>Code</summary>

```typescript
function getTabByTabId( tabs, tabId ) {

		return tabs.find( function ( tab ) {

			return tab.dom.id === tabId;

		} );

	}
```
</details>

### `toggleTabs(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `container.setHidden`
- `geometryTab.setHidden`
- `materialTab.setHidden`
- `scriptTab.setHidden`
- `container.select`
- `geometryTab.isHidden`
- `materialTab.isHidden`
- `scriptTab.isHidden`

**Internal Comments:**
```
// set active tab
```

<details><summary>Code</summary>

```typescript
function toggleTabs( object ) {

		container.setHidden( object === null );

		if ( object === null ) return;

		geometryTab.setHidden( ! object.geometry );

		materialTab.setHidden( ! object.material );

		scriptTab.setHidden( object === editor.camera );

		// set active tab

		if ( container.selected === 'geometryTab' ) {

			container.select( geometryTab.isHidden() ? 'objectTab' : 'geometryTab' );

		} else if ( container.selected === 'materialTab' ) {

			container.select( materialTab.isHidden() ? 'objectTab' : 'materialTab' );

		} else if ( container.selected === 'scriptTab' ) {

			container.select( scriptTab.isHidden() ? 'objectTab' : 'scriptTab' );

		}

	}
```
</details>


---