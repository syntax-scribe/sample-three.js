[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `publish.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 23 |
| 📊 Variables & Constants | 51 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`utils/docs/template/publish.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `htmlsafe` | `any` | let/var | `helper.htmlsafe` | ✗ |
| `linkto` | `any` | let/var | `helper.linkto` | ✗ |
| `resolveAuthorLinks` | `any` | let/var | `helper.resolveAuthorLinks` | ✗ |
| `hasOwnProp` | `(v: PropertyKey) => boolean` | let/var | `Object.prototype.hasOwnProperty` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `view` | `any` | let/var | `*not shown*` | ✗ |
| `themeOpts` | `any` | let/var | `( env.opts.themeOpts ) \|\| {}` | ✗ |
| `url` | `any` | let/var | `*not shown*` | ✗ |
| `needsSig` | `boolean` | let/var | `false` | ✗ |
| `itemName` | `any` | let/var | `item.name \|\| ''` | ✗ |
| `types` | `any[]` | let/var | `[]` | ✗ |
| `searchList` | `any[]` | let/var | `[]` | ✗ |
| `attribsString` | `string` | let/var | `''` | ✗ |
| `types` | `any[]` | let/var | `[]` | ✗ |
| `params` | `any` | let/var | `f.params ? addParamAttributes( f.params ) : []` | ✗ |
| `attribs` | `any[]` | let/var | `[]` | ✗ |
| `attribsString` | `string` | let/var | `''` | ✗ |
| `returnTypes` | `any[]` | let/var | `[]` | ✗ |
| `returnTypesString` | `string` | let/var | `''` | ✗ |
| `source` | `any` | let/var | `f.yields \|\| f.returns` | ✗ |
| `types` | `any[]` | let/var | `f.type ? buildItemTypeStrings( f ) : []` | ✗ |
| `html` | `any` | let/var | `*not shown*` | ✗ |
| `docData` | `{ env: any; title: any; docs: any; }` | let/var | `{ env: env, title: title, docs: docs }` | ✗ |
| `source` | `any` | let/var | `*not shown*` | ✗ |
| `coreDirectory` | `"src"` | let/var | `'src'` | ✗ |
| `addonsDirectory` | `"examples/jsm"` | let/var | `'examples/jsm'` | ✗ |
| `hierarchy` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `nav` | `string` | let/var | `''` | ✗ |
| `displayName` | `any` | let/var | `*not shown*` | ✗ |
| `itemNav` | `string` | let/var | `''` | ✗ |
| `path` | `any` | let/var | `item.meta.shortpath` | ✗ |
| `subCategory` | `any` | let/var | `path.split( '/' )[ 1 ]` | ✗ |
| `subCategory` | `any` | let/var | `path.split( '/' )[ 2 ]` | ✗ |
| `sortedMap` | `Map<any, any>` | let/var | `new Map( [ ...map.entries() ].sort() )` | ✗ |
| `navItems` | `string` | let/var | `''` | ✗ |
| `globalNav` | `any` | let/var | `*not shown*` | ✗ |
| `nav` | `string` | let/var | `''` | ✗ |
| `tslNav` | `string` | let/var | `''` | ✗ |
| `nav` | `string` | let/var | `''` | ✗ |
| `seen` | `{}` | let/var | `{}` | ✗ |
| `sourceFilePaths` | `any[]` | let/var | `[]` | ✗ |
| `sourceFiles` | `{}` | let/var | `{}` | ✗ |
| `staticFileFilter` | `any` | let/var | `*not shown*` | ✗ |
| `staticFilePaths` | `any` | let/var | `*not shown*` | ✗ |
| `staticFileScanner` | `any` | let/var | `*not shown*` | ✗ |
| `conf` | `any` | let/var | `env.conf.templates \|\| {}` | ✗ |
| `sourcePath` | `any` | let/var | `*not shown*` | ✗ |
| `docletPath` | `any` | let/var | `*not shown*` | ✗ |
| `url` | `any` | let/var | `helper.longnameToUrl[ doclet.longname ]` | ✗ |
| `tags` | `any` | let/var | `doclet.tags` | ✗ |
| `outputSourceFiles` | `boolean` | let/var | `conf.default && conf.default.outputSourceFiles !== false` | ✗ |


---

## Functions

### `mkdirSync(filepath: any): any`

**Parameters:**

- **`filepath`** `any`

**Returns:** `any`

**Calls:**

- `fs.mkdirSync`

<details><summary>Code</summary>

```typescript
function mkdirSync( filepath ) {

	return fs.mkdirSync( filepath, { recursive: true } );

}
```
</details>

### `find(spec: any): any`

**Parameters:**

- **`spec`** `any`

**Returns:** `any`

**Calls:**

- `helper.find`

<details><summary>Code</summary>

```typescript
function find( spec ) {

	return helper.find( data, spec );

}
```
</details>

### `getAncestorLinks(doclet: any): any`

**Parameters:**

- **`doclet`** `any`

**Returns:** `any`

**Calls:**

- `helper.getAncestorLinks`

<details><summary>Code</summary>

```typescript
function getAncestorLinks( doclet ) {

	return helper.getAncestorLinks( data, doclet );

}
```
</details>

### `hashToLink(doclet: any, hash: any): any`

**Parameters:**

- **`doclet`** `any`
- **`hash`** `any`

**Returns:** `any`

**Calls:**

- `/^(#.+)/.test`
- `helper.createLink`
- `url.replace`

<details><summary>Code</summary>

```typescript
function hashToLink( doclet, hash ) {

	let url;

	if ( ! /^(#.+)/.test( hash ) ) {

		return hash;

	}

	url = helper.createLink( doclet );
	url = url.replace( /(#.+|$)/, hash );

	return `<a href="${url}">${hash}</a>`;

}
```
</details>

### `needsSignature({ kind, type, meta }: any): boolean`

**Parameters:**

- **`{ kind, type, meta }`** `any`

**Returns:** `boolean`

**Calls:**

- `type.names[ i ].toLowerCase`
- `meta.code.type.match`

**Internal Comments:**
```
// function and class definitions always get a signature
// typedefs that contain functions get a signature, too
// and namespaces that are functions get a signature (but finding them is a (x3)
// bit messy) (x3)
```

<details><summary>Code</summary>

```typescript
function needsSignature( { kind, type, meta } ) {

	let needsSig = false;

	// function and class definitions always get a signature
	if ( kind === 'function' || kind === 'class' ) {

		needsSig = true;

	} else if ( kind === 'typedef' && type && type.names && type.names.length ) {

		// typedefs that contain functions get a signature, too

		for ( let i = 0, l = type.names.length; i < l; i ++ ) {

			if ( type.names[ i ].toLowerCase() === 'function' ) {

				needsSig = true;
				break;

			}

		}

	} else if ( kind === 'namespace' && meta && meta.code && meta.code.type && meta.code.type.match( /[Ff]unction/ ) ) {

		// and namespaces that are functions get a signature (but finding them is a
		// bit messy)

		needsSig = true;

	}

	return needsSig;

}
```
</details>

### `updateItemName(item: any): any`

**Parameters:**

- **`item`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function updateItemName( item ) {

	let itemName = item.name || '';

	if ( item.variable ) {

		itemName = `&hellip;${itemName}`;

	}

	return itemName;

}
```
</details>

### `addParamAttributes(params: any): any`

**Parameters:**

- **`params`** `any`

**Returns:** `any`

**Calls:**

- `params.filter( ( { name } ) => name && ! name.includes( '.' ) ).map`

<details><summary>Code</summary>

```typescript
function addParamAttributes( params ) {

	return params.filter( ( { name } ) => name && ! name.includes( '.' ) ).map( updateItemName );

}
```
</details>

### `buildItemTypeStrings(item: any): any[]`

**Parameters:**

- **`item`** `any`

**Returns:** `any[]`

**Calls:**

- `item.type.names.forEach`
- `types.push`
- `linkto`
- `htmlsafe`

<details><summary>Code</summary>

```typescript
function buildItemTypeStrings( item ) {

	const types = [];

	if ( item && item.type && item.type.names ) {

		item.type.names.forEach( name => {

			types.push( linkto( name, htmlsafe( name ) ) );

		} );

	}

	return types;

}
```
</details>

### `buildSearchListForData(): any[]`

**Returns:** `any[]`

**Calls:**

- `data().each`
- `searchList.push`
- `linkto`

<details><summary>Code</summary>

```typescript
function buildSearchListForData() {

	const searchList = [];

	data().each( ( item ) => {

		if ( item.kind !== 'package' && item.kind !== 'typedef' && ! item.inherited ) {

			searchList.push( {
				title: item.longname,
				link: linkto( item.longname, item.name ),
				description: item.description,
			} );

		}

	} );

	return searchList;

}
```
</details>

### `buildAttribsString(attribs: any): string`

**Parameters:**

- **`attribs`** `any`

**Returns:** `string`

**Calls:**

- `htmlsafe`
- `util.format`
- `attribs.join`

<details><summary>Code</summary>

```typescript
function buildAttribsString( attribs ) {

	let attribsString = '';

	if ( attribs && attribs.length ) {

		attribsString = htmlsafe( util.format( '(%s) ', attribs.join( ', ' ) ) );

	}

	return attribsString;

}
```
</details>

### `addNonParamAttributes(items: any): any[]`

**Parameters:**

- **`items`** `any`

**Returns:** `any[]`

**Calls:**

- `items.forEach`
- `types.concat`
- `buildItemTypeStrings`

<details><summary>Code</summary>

```typescript
function addNonParamAttributes( items ) {

	let types = [];

	items.forEach( item => {

		types = types.concat( buildItemTypeStrings( item ) );

	} );

	return types;

}
```
</details>

### `addSignatureParams(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `addParamAttributes`
- `util.format`
- `params.join`

<details><summary>Code</summary>

```typescript
function addSignatureParams( f ) {

	const params = f.params ? addParamAttributes( f.params ) : [];

	f.signature = util.format( '%s(%s)', ( f.signature || '' ), params.join( ', ' ) );

}
```
</details>

### `addSignatureReturns(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `source.forEach`
- `helper.getAttribs( item ).forEach`
- `attribs.includes`
- `attribs.push`
- `buildAttribsString`
- `addNonParamAttributes`
- `util.format`
- `returnTypes.join`

**Internal Comments:**
```
// jam all the return-type attributes into an array. this could create odd results (for example,
// if there are both nullable and non-nullable return types), but let's assume that most people
// who use multiple @return tags aren't using Closure Compiler type annotations, and vice-versa.
```

<details><summary>Code</summary>

```typescript
function addSignatureReturns( f ) {

	const attribs = [];
	let attribsString = '';
	let returnTypes = [];
	let returnTypesString = '';
	const source = f.yields || f.returns;

	// jam all the return-type attributes into an array. this could create odd results (for example,
	// if there are both nullable and non-nullable return types), but let's assume that most people
	// who use multiple @return tags aren't using Closure Compiler type annotations, and vice-versa.
	if ( source ) {

		source.forEach( item => {

			helper.getAttribs( item ).forEach( attrib => {

				if ( ! attribs.includes( attrib ) ) {

					attribs.push( attrib );

				}

			} );

		} );

		attribsString = buildAttribsString( attribs );

	}

	if ( source ) {

		returnTypes = addNonParamAttributes( source );

	}

	if ( returnTypes.length ) {

		returnTypesString = util.format( ' &rarr; %s{%s}', attribsString, returnTypes.join( '|' ) );

	}

	f.signature = `<span class="signature">${f.signature || ''}</span><span class="type-signature">${returnTypesString}</span>`;

}
```
</details>

### `addSignatureTypes(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `buildItemTypeStrings`
- `types.join`

<details><summary>Code</summary>

```typescript
function addSignatureTypes( f ) {

	const types = f.type ? buildItemTypeStrings( f ) : [];

	f.signature = `${f.signature || ''}<span class="type-signature">${types.length ? ` :${types.join( '|' )}` : ''}</span>`;

}
```
</details>

### `addAttribs(f: any): void`

**Parameters:**

- **`f`** `any`

**Returns:** `void`

**Calls:**

- `helper.getAttribs`
- `buildAttribsString`
- `util.format`

<details><summary>Code</summary>

```typescript
function addAttribs( f ) {

	const attribs = helper.getAttribs( f );
	const attribsString = buildAttribsString( attribs );

	f.attribs = util.format( '<span class="type-signature">%s</span>', attribsString );

}
```
</details>

### `shortenPaths(files: any, commonPrefix: any): any`

**Parameters:**

- **`files`** `any`
- **`commonPrefix`** `any`

**Returns:** `any`

**Calls:**

- `Object.keys( files ).forEach`
- `files[ file ].resolved.replace( commonPrefix, '' )
		// always use forward slashes
			.replace`

<details><summary>Code</summary>

```typescript
function shortenPaths( files, commonPrefix ) {

	Object.keys( files ).forEach( file => {

		files[ file ].shortened = files[ file ].resolved.replace( commonPrefix, '' )
		// always use forward slashes
			.replace( /\\/g, '/' );

	} );

	return files;

}
```
</details>

### `getPathFromDoclet({ meta }: any): any`

**Parameters:**

- **`{ meta }`** `any`

**Returns:** `any`

**Calls:**

- `path.join`

<details><summary>Code</summary>

```typescript
function getPathFromDoclet( { meta } ) {

	if ( ! meta ) {

		return null;

	}

	return meta.path && meta.path !== 'null' ?
		path.join( meta.path, meta.filename ) :
		meta.filename;

}
```
</details>

### `generate(title: any, docs: any, filename: any, resolveLinks: any): void`

**Parameters:**

- **`title`** `any`
- **`docs`** `any`
- **`filename`** `any`
- **`resolveLinks`** `any`

**Returns:** `void`

**Calls:**

- `path.join`
- `view.render`
- `helper.resolveLinks`
- `fs.writeFileSync`

<details><summary>Code</summary>

```typescript
function generate( title, docs, filename, resolveLinks ) {

	let html;

	resolveLinks = resolveLinks !== false;

	const docData = {
		env: env,
		title: title,
		docs: docs
	};

	const outpath = path.join( outdir, filename );
	html = view.render( 'container.tmpl', docData );

	if ( resolveLinks ) {

		html = helper.resolveLinks( html ); // turn {@link foo} into <a href="foodoc.html">foo</a>

	}

	fs.writeFileSync( outpath, html, 'utf8' );

}
```
</details>

### `generateSourceFiles(sourceFiles: any, encoding: string): void`

**Parameters:**

- **`sourceFiles`** `any`
- **`encoding`** `string`

**Returns:** `void`

**Calls:**

- `Object.keys( sourceFiles ).forEach`
- `helper.getUniqueFilename`
- `helper.registerLink`
- `helper.htmlsafe`
- `fs.readFileSync`
- `logger.error`
- `generate`

**Internal Comments:**
```
// links are keyed to the shortened path in each doclet's `meta.shortpath` property (x2)
```

<details><summary>Code</summary>

```typescript
function generateSourceFiles( sourceFiles, encoding = 'utf8' ) {

	Object.keys( sourceFiles ).forEach( file => {

		let source;
		// links are keyed to the shortened path in each doclet's `meta.shortpath` property
		const sourceOutfile = helper.getUniqueFilename( sourceFiles[ file ].shortened );

		helper.registerLink( sourceFiles[ file ].shortened, sourceOutfile );

		try {

			source = {
				kind: 'source',
				code: helper.htmlsafe( fs.readFileSync( sourceFiles[ file ].resolved, encoding ) )
			};

		} catch ( e ) {

			logger.error( 'Error while generating source file %s: %s', file, e.message );

		}

		generate( `Source: ${sourceFiles[ file ].shortened}`, [ source ], sourceOutfile,
			false );

	} );

}
```
</details>

### `buildMainNav(items: any, itemsSeen: any, linktoFn: any): string`

**Parameters:**

- **`items`** `any`
- **`itemsSeen`** `any`
- **`linktoFn`** `any`

**Returns:** `string`

**Calls:**

- `hierarchy.set`
- `items.forEach`
- `hasOwnProp.call`
- `linktoFn`
- `displayName.replace`
- `path.startsWith`
- `path.split`
- `pushNavItem`
- `[ ...map.entries() ].sort`
- `map.entries`
- `links.sort`

<details><summary>Code</summary>

```typescript
function buildMainNav( items, itemsSeen, linktoFn ) {

	const coreDirectory = 'src';
	const addonsDirectory = 'examples/jsm';

	const hierarchy = new Map();
	hierarchy.set( 'Core', new Map() );
	hierarchy.set( 'Addons', new Map() );

	let nav = '';

	if ( items.length ) {

		items.forEach( item => {

			let displayName;
			let itemNav = '';

			if ( ! hasOwnProp.call( itemsSeen, item.longname ) ) {

				if ( env.conf.templates.default.useLongnameInNav ) {

					displayName = item.longname;

				} else {

					displayName = item.name;

				}

				itemNav += `<li data-name="${item.name}">${linktoFn( item.longname, displayName.replace( /\b(module|event):/g, '' ) )}</li>`;

				itemsSeen[ item.longname ] = true;

				const path = item.meta.shortpath;

				if ( path.startsWith( coreDirectory ) ) {

					const subCategory = path.split( '/' )[ 1 ];

					pushNavItem( hierarchy, 'Core', subCategory, itemNav );

				} else if ( path.startsWith( addonsDirectory ) ) {

					const subCategory = path.split( '/' )[ 2 ];

					pushNavItem( hierarchy, 'Addons', subCategory, itemNav );

				}

			}

		} );

		for ( const [ mainCategory, map ] of hierarchy ) {

			nav += `<h2>${mainCategory}</h2>`;

			const sortedMap = new Map( [ ...map.entries() ].sort() ); // sort sub categories

			for ( const [ subCategory, links ] of sortedMap ) {

				nav += `<h3>${subCategory}</h3>`;

				let navItems = '';

				links.sort();

				for ( const link of links ) {

					navItems += link;

				}

				nav += `<ul>${navItems}</ul>`;

			}

		}

	}

	return nav;

}
```
</details>

### `buildGlobalsNav(globals: any, seen: any): string`

**Parameters:**

- **`globals`** `any`
- **`seen`** `any`

**Returns:** `string`

**Calls:**

- `globals.forEach`
- `hasOwnProp.call`
- `Array.isArray`
- `tags.find`
- `linkto`

**Internal Comments:**
```
// TSL (x2)
// Globals (x3)
// turn the heading into a link so you can actually get to the global page (x3)
```

<details><summary>Code</summary>

```typescript
function buildGlobalsNav( globals, seen ) {

	let globalNav;
	let nav = '';

	if ( globals.length ) {

		// TSL

		let tslNav = '';

		globals.forEach( ( { kind, longname, name, tags } ) => {

			if ( kind !== 'typedef' && ! hasOwnProp.call( seen, longname ) && Array.isArray( tags ) ) {

				const tslTag = tags.find( tag => tag.title === 'tsl' );

				if ( tslTag !== undefined ) {

					tslNav += `<li data-name="${longname}">${linkto( longname, name )}</li>`;

					seen[ longname ] = true;

				}

			}

		} );

		nav += `<h2>TSL</h2><ul>${tslNav}</ul>`;

		// Globals

		globalNav = '';

		globals.forEach( ( { kind, longname, name } ) => {

			if ( kind !== 'typedef' && ! hasOwnProp.call( seen, longname ) ) {

				globalNav += `<li data-name="${longname}">${linkto( longname, name )}</li>`;

			}

			seen[ longname ] = true;

		} );

		if ( ! globalNav ) {

			// turn the heading into a link so you can actually get to the global page
			nav += `<h3>${linkto( 'global', 'Global' )}</h3>`;

		} else {

			nav += `<h2>Global</h2><ul>${globalNav}</ul>`;

		}

	}

	return nav;

}
```
</details>

### `pushNavItem(hierarchy: any, mainCategory: any, subCategory: any, itemNav: any): void`

**Parameters:**

- **`hierarchy`** `any`
- **`mainCategory`** `any`
- **`subCategory`** `any`
- **`itemNav`** `any`

**Returns:** `void`

**Calls:**

- `subCategory[ 0 ].toUpperCase`
- `subCategory.slice`
- `hierarchy.get( mainCategory ).get`
- `hierarchy.get( mainCategory ).set`
- `categoryList.push`

<details><summary>Code</summary>

```typescript
function pushNavItem( hierarchy, mainCategory, subCategory, itemNav ) {

	subCategory = subCategory[ 0 ].toUpperCase() + subCategory.slice( 1 ); // capitalize

	if ( hierarchy.get( mainCategory ).get( subCategory ) === undefined ) {

		hierarchy.get( mainCategory ).set( subCategory, [] );

	}

	const categoryList = hierarchy.get( mainCategory ).get( subCategory );

	categoryList.push( itemNav );

}
```
</details>

### `buildNav(members: any): string`

**JSDoc:**
```typescript
/**
 * Create the navigation sidebar.
 * @param {Object} members The members that will be used to create the sidebar.
 * @return {string} The HTML for the navigation sidebar.
 */
```

**Parameters:**

- **`members`** `any`

**Returns:** `string`

**Calls:**

- `buildMainNav`
- `buildGlobalsNav`

<details><summary>Code</summary>

```typescript
function buildNav( members ) {

	let nav = '';
	const seen = {};

	nav += buildMainNav( [ ...members.classes, ...members.modules ], seen, linkto );
	nav += buildGlobalsNav( members.globals, seen );

	return nav;

}
```
</details>


---