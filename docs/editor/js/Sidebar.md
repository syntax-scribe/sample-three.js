[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UITabbedPanel` | `./libs/ui.js` |
| `UISpan` | `./libs/ui.js` |
| `SidebarScene` | `./Sidebar.Scene.js` |
| `SidebarProperties` | `./Sidebar.Properties.js` |
| `SidebarProject` | `./Sidebar.Project.js` |
| `SidebarSettings` | `./Sidebar.Settings.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UITabbedPanel` | let/var | `new UITabbedPanel()` | ✗ |
| `sidebarProperties` | `any` | let/var | `new SidebarProperties( editor )` | ✗ |
| `project` | `any` | let/var | `new SidebarProject( editor )` | ✗ |
| `settings` | `any` | let/var | `new SidebarSettings( editor )` | ✗ |
| `sidebarPropertiesResizeObse...` | `ResizeObserver` | let/var | `new ResizeObserver( function () { sidebarProperties.tabsDiv.setWidth( getComp...` | ✗ |


---

## Functions

### `Sidebar(editor: any): UITabbedPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UITabbedPanel`

**Calls:**

- `container.setId`
- `new UISpan().add`
- `container.addTab`
- `strings.getKey`
- `container.select`
- `sidebarProperties.tabsDiv.setWidth`
- `getComputedStyle`
- `sidebarPropertiesResizeObserver.observe`

<details><summary>Code</summary>

```typescript
function Sidebar( editor ) {

	const strings = editor.strings;

	const container = new UITabbedPanel();
	container.setId( 'sidebar' );

	const sidebarProperties = new SidebarProperties( editor );

	const scene = new UISpan().add(
		new SidebarScene( editor ),
		sidebarProperties
	);
	const project = new SidebarProject( editor );
	const settings = new SidebarSettings( editor );

	container.addTab( 'scene', strings.getKey( 'sidebar/scene' ), scene );
	container.addTab( 'project', strings.getKey( 'sidebar/project' ), project );
	container.addTab( 'settings', strings.getKey( 'sidebar/settings' ), settings );
	container.select( 'scene' );

	const sidebarPropertiesResizeObserver = new ResizeObserver( function () {

		sidebarProperties.tabsDiv.setWidth( getComputedStyle( container.dom ).width );

	} );

	sidebarPropertiesResizeObserver.observe( container.tabsDiv.dom );

	return container;

}
```
</details>


---