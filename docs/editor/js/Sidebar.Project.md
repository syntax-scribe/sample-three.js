[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Project.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Project.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UISpan` | `./libs/ui.js` |
| `SidebarProjectApp` | `./Sidebar.Project.App.js` |
| `SidebarProjectRenderer` | `./Sidebar.Project.Renderer.js` |
| `SidebarProjectImage` | `./Sidebar.Project.Image.js` |
| `SidebarProjectVideo` | `./Sidebar.Project.Video.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `container` | `UISpan` | let/var | `new UISpan()` | ✗ |


---

## Functions

### `SidebarProject(editor: any): UISpan`

**Parameters:**

- **`editor`** `any`

**Returns:** `UISpan`

**Calls:**

- `container.add`

**Internal Comments:**
```
/* container.add( new SidebarProjectMaterials( editor ) ); */ (x4)
```

<details><summary>Code</summary>

```typescript
function SidebarProject( editor ) {

	const container = new UISpan();

	container.add( new SidebarProjectRenderer( editor ) );

	/* container.add( new SidebarProjectMaterials( editor ) ); */

	container.add( new SidebarProjectApp( editor ) );

	container.add( new SidebarProjectImage( editor ) );

	if ( 'SharedArrayBuffer' in window ) {

		container.add( new SidebarProjectVideo( editor ) );

	}

	return container;

}
```
</details>


---