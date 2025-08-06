[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Menubar.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Menubar.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `MenubarAdd` | `./Menubar.Add.js` |
| `MenubarEdit` | `./Menubar.Edit.js` |
| `MenubarFile` | `./Menubar.File.js` |
| `MenubarView` | `./Menubar.View.js` |
| `MenubarHelp` | `./Menubar.Help.js` |
| `MenubarStatus` | `./Menubar.Status.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |


---

## Functions

### `Menubar(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setId`
- `container.add`

<details><summary>Code</summary>

```typescript
function Menubar( editor ) {

	const container = new UIPanel();
	container.setId( 'menubar' );

	container.add( new MenubarFile( editor ) );
	container.add( new MenubarEdit( editor ) );
	container.add( new MenubarAdd( editor ) );
	container.add( new MenubarView( editor ) );
	container.add( new MenubarHelp( editor ) );

	container.add( new MenubarStatus( editor ) );

	return container;

}
```
</details>


---