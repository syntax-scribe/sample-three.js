[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BVHLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/BVHLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationClip` | `three` |
| `Bone` | `three` |
| `FileLoader` | `three` |
| `Loader` | `three` |
| `Quaternion` | `three` |
| `QuaternionKeyframeTrack` | `three` |
| `Skeleton` | `three` |
| `Vector3` | `three` |
| `VectorKeyframeTrack` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `list` | `any[]` | let/var | `[]` | ✗ |
| `keyframe` | `{ time: any; position: any; rotation:...` | let/var | `{ time: frameTime, position: new Vector3(), rotation: new Quaternion() }` | ✗ |
| `quat` | `any` | let/var | `new Quaternion()` | ✗ |
| `vx` | `any` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `vy` | `any` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `vz` | `any` | let/var | `new Vector3( 0, 0, 1 )` | ✗ |
| `node` | `{ name: string; type: string; frames:...` | let/var | `{ name: '', type: '', frames: [] }` | ✗ |
| `offset` | `any` | let/var | `new Vector3( parseFloat( tokens[ 1 ] ), parseFloat( tokens[ 2 ] ), parseFloat...` | ✗ |
| `bone` | `any` | let/var | `new Bone()` | ✗ |
| `tracks` | `any[]` | let/var | `[]` | ✗ |
| `bone` | `any` | let/var | `bones[ i ]` | ✗ |
| `times` | `any[]` | let/var | `[]` | ✗ |
| `positions` | `any[]` | let/var | `[]` | ✗ |
| `rotations` | `any[]` | let/var | `[]` | ✗ |
| `frame` | `any` | let/var | `bone.frames[ j ]` | ✗ |
| `line` | `any` | let/var | `*not shown*` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `threeBones` | `any[]` | let/var | `[]` | ✗ |


---

## Functions

### `BVHLoader.load(url: string, onLoad: (arg0: { skeleton: Skeleton; clip: AnimationClip; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded BVH asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({skeleton:Skeleton,clip:AnimationClip})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { skeleton: Skeleton; clip: AnimationClip; }) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `onLoad`
- `scope.parse`
- `onError`
- `console.error`
- `scope.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `BVHLoader.parse(text: string): { skeleton: Skeleton; clip: AnimationClip; }`

**JSDoc:**
```typescript
/**
	 * Parses the given BVH data and returns the resulting data.
	 *
	 * @param {string} text - The raw BVH data as a string.
	 * @return {{skeleton:Skeleton,clip:AnimationClip}} An object representing the parsed asset.
	 */
```

**Parameters:**

- **`text`** `string`

**Returns:** `{ skeleton: Skeleton; clip: AnimationClip; }`

**Calls:**

- `nextLine`
- `console.error`
- `readNode`
- `nextLine( lines ).split`
- `parseInt`
- `isNaN`
- `parseFloat`
- `readFrameData`
- `bone.frames.push`
- `data.shift().trim`
- `quat.setFromAxisAngle`
- `keyframe.rotation.multiply`
- `console.warn`
- `list.push`
- `firstline.split`
- `tokens[ 0 ].toUpperCase`
- `tokens[ 1 ].toUpperCase`
- `tokens.splice`
- `node.children.push`
- `bone.position.add`
- `bone.add`
- `toTHREEBone`
- `times.push`
- `positions.push`
- `rotations.push`
- `tracks.push`
- `lines.shift().trim`
- `text.split`
- `readBvh`
- `toTHREEAnimation`

**Internal Comments:**
```
// reads a string array (lines) from a BVH file
// and outputs a skeleton structure including motion data
// returns thee root node:
// { name: '', channels: [], children: [] }
// read model structure
// read motion data
// number of frames (x2)
// frame time (x3)
// read frame data line by line
/*
			Recursively reads data from a single frame into the bone hierarchy.
			The passed bone hierarchy has to be structured in the same order as the BVH file.
			keyframe data is stored in bone.frames.

			- data: splitted string array (frame values), values are shift()ed so
			this should be empty after parsing the whole hierarchy.
			- frameTime: playback time for this keyframe.
			- bone: the bone to read frame data from.
		*/
// end sites have no motion data
// add keyframe (x2)
// parse values for each channel in node
// parse child nodes
/*
		 Recursively parses the HIERARCHY section of the BVH file

		 - lines: all lines of the file. lines are consumed as we go along.
		 - firstline: line containing the node type and name e.g. 'JOINT hip'
		 - list: collects a flat list of nodes

		 returns: a BVH node including children
		*/
// parse node type and name (x2)
// parse OFFSET (x3)
// parse CHANNELS definitions
// read children
/*
			recursively converts the internal bvh node structure to a Bone hierarchy

			source: the bvh root node
			list: pass an empty array, collects a flat list of all converted THREE.Bones

			returns the root Bone
		*/
/*
			builds an AnimationClip from the keyframe data saved in each bone.

			bone: bvh root node

			returns: an AnimationClip containing position and quaternion tracks
		*/
// create a position and quaternion animation track for each node
// track data (x2)
// the animation system animates the position property, (x4)
// so we have to add the joint offset to all values (x4)
/*
			returns the next non-empty line in lines
		*/
// skip empty lines
```

<details><summary>Code</summary>

```typescript
parse( text ) {

		// reads a string array (lines) from a BVH file
		// and outputs a skeleton structure including motion data

		// returns thee root node:
		// { name: '', channels: [], children: [] }
		function readBvh( lines ) {

			// read model structure

			if ( nextLine( lines ) !== 'HIERARCHY' ) {

				console.error( 'THREE.BVHLoader: HIERARCHY expected.' );

			}

			const list = []; // collects flat array of all bones
			const root = readNode( lines, nextLine( lines ), list );

			// read motion data

			if ( nextLine( lines ) !== 'MOTION' ) {

				console.error( 'THREE.BVHLoader: MOTION expected.' );

			}

			// number of frames

			let tokens = nextLine( lines ).split( /[\s]+/ );
			const numFrames = parseInt( tokens[ 1 ] );

			if ( isNaN( numFrames ) ) {

				console.error( 'THREE.BVHLoader: Failed to read number of frames.' );

			}

			// frame time

			tokens = nextLine( lines ).split( /[\s]+/ );
			const frameTime = parseFloat( tokens[ 2 ] );

			if ( isNaN( frameTime ) ) {

				console.error( 'THREE.BVHLoader: Failed to read frame time.' );

			}

			// read frame data line by line

			for ( let i = 0; i < numFrames; i ++ ) {

				tokens = nextLine( lines ).split( /[\s]+/ );
				readFrameData( tokens, i * frameTime, root );

			}

			return list;

		}

		/*
			Recursively reads data from a single frame into the bone hierarchy.
			The passed bone hierarchy has to be structured in the same order as the BVH file.
			keyframe data is stored in bone.frames.

			- data: splitted string array (frame values), values are shift()ed so
			this should be empty after parsing the whole hierarchy.
			- frameTime: playback time for this keyframe.
			- bone: the bone to read frame data from.
		*/
		function readFrameData( data, frameTime, bone ) {

			// end sites have no motion data

			if ( bone.type === 'ENDSITE' ) return;

			// add keyframe

			const keyframe = {
				time: frameTime,
				position: new Vector3(),
				rotation: new Quaternion()
			};

			bone.frames.push( keyframe );

			const quat = new Quaternion();

			const vx = new Vector3( 1, 0, 0 );
			const vy = new Vector3( 0, 1, 0 );
			const vz = new Vector3( 0, 0, 1 );

			// parse values for each channel in node

			for ( let i = 0; i < bone.channels.length; i ++ ) {

				switch ( bone.channels[ i ] ) {

					case 'Xposition':
						keyframe.position.x = parseFloat( data.shift().trim() );
						break;
					case 'Yposition':
						keyframe.position.y = parseFloat( data.shift().trim() );
						break;
					case 'Zposition':
						keyframe.position.z = parseFloat( data.shift().trim() );
						break;
					case 'Xrotation':
						quat.setFromAxisAngle( vx, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					case 'Yrotation':
						quat.setFromAxisAngle( vy, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					case 'Zrotation':
						quat.setFromAxisAngle( vz, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					default:
						console.warn( 'THREE.BVHLoader: Invalid channel type.' );

				}

			}

			// parse child nodes

			for ( let i = 0; i < bone.children.length; i ++ ) {

				readFrameData( data, frameTime, bone.children[ i ] );

			}

		}

		/*
		 Recursively parses the HIERARCHY section of the BVH file

		 - lines: all lines of the file. lines are consumed as we go along.
		 - firstline: line containing the node type and name e.g. 'JOINT hip'
		 - list: collects a flat list of nodes

		 returns: a BVH node including children
		*/
		function readNode( lines, firstline, list ) {

			const node = { name: '', type: '', frames: [] };
			list.push( node );

			// parse node type and name

			let tokens = firstline.split( /[\s]+/ );

			if ( tokens[ 0 ].toUpperCase() === 'END' && tokens[ 1 ].toUpperCase() === 'SITE' ) {

				node.type = 'ENDSITE';
				node.name = 'ENDSITE'; // bvh end sites have no name

			} else {

				node.name = tokens[ 1 ];
				node.type = tokens[ 0 ].toUpperCase();

			}

			if ( nextLine( lines ) !== '{' ) {

				console.error( 'THREE.BVHLoader: Expected opening { after type & name' );

			}

			// parse OFFSET

			tokens = nextLine( lines ).split( /[\s]+/ );

			if ( tokens[ 0 ] !== 'OFFSET' ) {

				console.error( 'THREE.BVHLoader: Expected OFFSET but got: ' + tokens[ 0 ] );

			}

			if ( tokens.length !== 4 ) {

				console.error( 'THREE.BVHLoader: Invalid number of values for OFFSET.' );

			}

			const offset = new Vector3(
				parseFloat( tokens[ 1 ] ),
				parseFloat( tokens[ 2 ] ),
				parseFloat( tokens[ 3 ] )
			);

			if ( isNaN( offset.x ) || isNaN( offset.y ) || isNaN( offset.z ) ) {

				console.error( 'THREE.BVHLoader: Invalid values of OFFSET.' );

			}

			node.offset = offset;

			// parse CHANNELS definitions

			if ( node.type !== 'ENDSITE' ) {

				tokens = nextLine( lines ).split( /[\s]+/ );

				if ( tokens[ 0 ] !== 'CHANNELS' ) {

					console.error( 'THREE.BVHLoader: Expected CHANNELS definition.' );

				}

				const numChannels = parseInt( tokens[ 1 ] );
				node.channels = tokens.splice( 2, numChannels );
				node.children = [];

			}

			// read children

			while ( true ) {

				const line = nextLine( lines );

				if ( line === '}' ) {

					return node;

				} else {

					node.children.push( readNode( lines, line, list ) );

				}

			}

		}

		/*
			recursively converts the internal bvh node structure to a Bone hierarchy

			source: the bvh root node
			list: pass an empty array, collects a flat list of all converted THREE.Bones

			returns the root Bone
		*/
		function toTHREEBone( source, list ) {

			const bone = new Bone();
			list.push( bone );

			bone.position.add( source.offset );
			bone.name = source.name;

			if ( source.type !== 'ENDSITE' ) {

				for ( let i = 0; i < source.children.length; i ++ ) {

					bone.add( toTHREEBone( source.children[ i ], list ) );

				}

			}

			return bone;

		}

		/*
			builds an AnimationClip from the keyframe data saved in each bone.

			bone: bvh root node

			returns: an AnimationClip containing position and quaternion tracks
		*/
		function toTHREEAnimation( bones ) {

			const tracks = [];

			// create a position and quaternion animation track for each node

			for ( let i = 0; i < bones.length; i ++ ) {

				const bone = bones[ i ];

				if ( bone.type === 'ENDSITE' )
					continue;

				// track data

				const times = [];
				const positions = [];
				const rotations = [];

				for ( let j = 0; j < bone.frames.length; j ++ ) {

					const frame = bone.frames[ j ];

					times.push( frame.time );

					// the animation system animates the position property,
					// so we have to add the joint offset to all values

					positions.push( frame.position.x + bone.offset.x );
					positions.push( frame.position.y + bone.offset.y );
					positions.push( frame.position.z + bone.offset.z );

					rotations.push( frame.rotation.x );
					rotations.push( frame.rotation.y );
					rotations.push( frame.rotation.z );
					rotations.push( frame.rotation.w );

				}

				if ( scope.animateBonePositions ) {

					tracks.push( new VectorKeyframeTrack( bone.name + '.position', times, positions ) );

				}

				if ( scope.animateBoneRotations ) {

					tracks.push( new QuaternionKeyframeTrack( bone.name + '.quaternion', times, rotations ) );

				}

			}

			return new AnimationClip( 'animation', - 1, tracks );

		}

		/*
			returns the next non-empty line in lines
		*/
		function nextLine( lines ) {

			let line;
			// skip empty lines
			while ( ( line = lines.shift().trim() ).length === 0 ) { }

			return line;

		}

		const scope = this;

		const lines = text.split( /[\r\n]+/g );

		const bones = readBvh( lines );

		const threeBones = [];
		toTHREEBone( bones[ 0 ], threeBones );

		const threeClip = toTHREEAnimation( bones );

		return {
			skeleton: new Skeleton( threeBones ),
			clip: threeClip
		};

	}
```
</details>

### `readBvh(lines: any): any[]`

**Parameters:**

- **`lines`** `any`

**Returns:** `any[]`

**Calls:**

- `nextLine`
- `console.error`
- `readNode`
- `nextLine( lines ).split`
- `parseInt`
- `isNaN`
- `parseFloat`
- `readFrameData`

**Internal Comments:**
```
// read model structure
// read motion data
// number of frames (x2)
// frame time (x3)
// read frame data line by line
```

<details><summary>Code</summary>

```typescript
function readBvh( lines ) {

			// read model structure

			if ( nextLine( lines ) !== 'HIERARCHY' ) {

				console.error( 'THREE.BVHLoader: HIERARCHY expected.' );

			}

			const list = []; // collects flat array of all bones
			const root = readNode( lines, nextLine( lines ), list );

			// read motion data

			if ( nextLine( lines ) !== 'MOTION' ) {

				console.error( 'THREE.BVHLoader: MOTION expected.' );

			}

			// number of frames

			let tokens = nextLine( lines ).split( /[\s]+/ );
			const numFrames = parseInt( tokens[ 1 ] );

			if ( isNaN( numFrames ) ) {

				console.error( 'THREE.BVHLoader: Failed to read number of frames.' );

			}

			// frame time

			tokens = nextLine( lines ).split( /[\s]+/ );
			const frameTime = parseFloat( tokens[ 2 ] );

			if ( isNaN( frameTime ) ) {

				console.error( 'THREE.BVHLoader: Failed to read frame time.' );

			}

			// read frame data line by line

			for ( let i = 0; i < numFrames; i ++ ) {

				tokens = nextLine( lines ).split( /[\s]+/ );
				readFrameData( tokens, i * frameTime, root );

			}

			return list;

		}
```
</details>

### `readFrameData(data: any, frameTime: any, bone: any): void`

**Parameters:**

- **`data`** `any`
- **`frameTime`** `any`
- **`bone`** `any`

**Returns:** `void`

**Calls:**

- `bone.frames.push`
- `parseFloat`
- `data.shift().trim`
- `quat.setFromAxisAngle`
- `keyframe.rotation.multiply`
- `console.warn`
- `readFrameData`

**Internal Comments:**
```
// end sites have no motion data
// add keyframe (x2)
// parse values for each channel in node
// parse child nodes
```

<details><summary>Code</summary>

```typescript
function readFrameData( data, frameTime, bone ) {

			// end sites have no motion data

			if ( bone.type === 'ENDSITE' ) return;

			// add keyframe

			const keyframe = {
				time: frameTime,
				position: new Vector3(),
				rotation: new Quaternion()
			};

			bone.frames.push( keyframe );

			const quat = new Quaternion();

			const vx = new Vector3( 1, 0, 0 );
			const vy = new Vector3( 0, 1, 0 );
			const vz = new Vector3( 0, 0, 1 );

			// parse values for each channel in node

			for ( let i = 0; i < bone.channels.length; i ++ ) {

				switch ( bone.channels[ i ] ) {

					case 'Xposition':
						keyframe.position.x = parseFloat( data.shift().trim() );
						break;
					case 'Yposition':
						keyframe.position.y = parseFloat( data.shift().trim() );
						break;
					case 'Zposition':
						keyframe.position.z = parseFloat( data.shift().trim() );
						break;
					case 'Xrotation':
						quat.setFromAxisAngle( vx, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					case 'Yrotation':
						quat.setFromAxisAngle( vy, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					case 'Zrotation':
						quat.setFromAxisAngle( vz, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					default:
						console.warn( 'THREE.BVHLoader: Invalid channel type.' );

				}

			}

			// parse child nodes

			for ( let i = 0; i < bone.children.length; i ++ ) {

				readFrameData( data, frameTime, bone.children[ i ] );

			}

		}
```
</details>

### `readNode(lines: any, firstline: any, list: any): { name: string; type: string; frames: any[]; }`

**Parameters:**

- **`lines`** `any`
- **`firstline`** `any`
- **`list`** `any`

**Returns:** `{ name: string; type: string; frames: any[]; }`

**Calls:**

- `list.push`
- `firstline.split`
- `tokens[ 0 ].toUpperCase`
- `tokens[ 1 ].toUpperCase`
- `nextLine`
- `console.error`
- `nextLine( lines ).split`
- `parseFloat`
- `isNaN`
- `parseInt`
- `tokens.splice`
- `node.children.push`
- `readNode`

**Internal Comments:**
```
// parse node type and name (x2)
// parse OFFSET (x3)
// parse CHANNELS definitions
// read children
```

<details><summary>Code</summary>

```typescript
function readNode( lines, firstline, list ) {

			const node = { name: '', type: '', frames: [] };
			list.push( node );

			// parse node type and name

			let tokens = firstline.split( /[\s]+/ );

			if ( tokens[ 0 ].toUpperCase() === 'END' && tokens[ 1 ].toUpperCase() === 'SITE' ) {

				node.type = 'ENDSITE';
				node.name = 'ENDSITE'; // bvh end sites have no name

			} else {

				node.name = tokens[ 1 ];
				node.type = tokens[ 0 ].toUpperCase();

			}

			if ( nextLine( lines ) !== '{' ) {

				console.error( 'THREE.BVHLoader: Expected opening { after type & name' );

			}

			// parse OFFSET

			tokens = nextLine( lines ).split( /[\s]+/ );

			if ( tokens[ 0 ] !== 'OFFSET' ) {

				console.error( 'THREE.BVHLoader: Expected OFFSET but got: ' + tokens[ 0 ] );

			}

			if ( tokens.length !== 4 ) {

				console.error( 'THREE.BVHLoader: Invalid number of values for OFFSET.' );

			}

			const offset = new Vector3(
				parseFloat( tokens[ 1 ] ),
				parseFloat( tokens[ 2 ] ),
				parseFloat( tokens[ 3 ] )
			);

			if ( isNaN( offset.x ) || isNaN( offset.y ) || isNaN( offset.z ) ) {

				console.error( 'THREE.BVHLoader: Invalid values of OFFSET.' );

			}

			node.offset = offset;

			// parse CHANNELS definitions

			if ( node.type !== 'ENDSITE' ) {

				tokens = nextLine( lines ).split( /[\s]+/ );

				if ( tokens[ 0 ] !== 'CHANNELS' ) {

					console.error( 'THREE.BVHLoader: Expected CHANNELS definition.' );

				}

				const numChannels = parseInt( tokens[ 1 ] );
				node.channels = tokens.splice( 2, numChannels );
				node.children = [];

			}

			// read children

			while ( true ) {

				const line = nextLine( lines );

				if ( line === '}' ) {

					return node;

				} else {

					node.children.push( readNode( lines, line, list ) );

				}

			}

		}
```
</details>

### `toTHREEBone(source: any, list: any): any`

**Parameters:**

- **`source`** `any`
- **`list`** `any`

**Returns:** `any`

**Calls:**

- `list.push`
- `bone.position.add`
- `bone.add`
- `toTHREEBone`

<details><summary>Code</summary>

```typescript
function toTHREEBone( source, list ) {

			const bone = new Bone();
			list.push( bone );

			bone.position.add( source.offset );
			bone.name = source.name;

			if ( source.type !== 'ENDSITE' ) {

				for ( let i = 0; i < source.children.length; i ++ ) {

					bone.add( toTHREEBone( source.children[ i ], list ) );

				}

			}

			return bone;

		}
```
</details>

### `toTHREEAnimation(bones: any): any`

**Parameters:**

- **`bones`** `any`

**Returns:** `any`

**Calls:**

- `times.push`
- `positions.push`
- `rotations.push`
- `tracks.push`

**Internal Comments:**
```
// create a position and quaternion animation track for each node
// track data (x2)
// the animation system animates the position property, (x4)
// so we have to add the joint offset to all values (x4)
```

<details><summary>Code</summary>

```typescript
function toTHREEAnimation( bones ) {

			const tracks = [];

			// create a position and quaternion animation track for each node

			for ( let i = 0; i < bones.length; i ++ ) {

				const bone = bones[ i ];

				if ( bone.type === 'ENDSITE' )
					continue;

				// track data

				const times = [];
				const positions = [];
				const rotations = [];

				for ( let j = 0; j < bone.frames.length; j ++ ) {

					const frame = bone.frames[ j ];

					times.push( frame.time );

					// the animation system animates the position property,
					// so we have to add the joint offset to all values

					positions.push( frame.position.x + bone.offset.x );
					positions.push( frame.position.y + bone.offset.y );
					positions.push( frame.position.z + bone.offset.z );

					rotations.push( frame.rotation.x );
					rotations.push( frame.rotation.y );
					rotations.push( frame.rotation.z );
					rotations.push( frame.rotation.w );

				}

				if ( scope.animateBonePositions ) {

					tracks.push( new VectorKeyframeTrack( bone.name + '.position', times, positions ) );

				}

				if ( scope.animateBoneRotations ) {

					tracks.push( new QuaternionKeyframeTrack( bone.name + '.quaternion', times, rotations ) );

				}

			}

			return new AnimationClip( 'animation', - 1, tracks );

		}
```
</details>

### `nextLine(lines: any): any`

**Parameters:**

- **`lines`** `any`

**Returns:** `any`

**Calls:**

- `lines.shift().trim`

**Internal Comments:**
```
// skip empty lines
```

<details><summary>Code</summary>

```typescript
function nextLine( lines ) {

			let line;
			// skip empty lines
			while ( ( line = lines.shift().trim() ).length === 0 ) { }

			return line;

		}
```
</details>


---

## Classes

### `BVHLoader`

<details><summary>Class Code</summary>

```ts
class BVHLoader extends Loader {

	/**
	 * Constructs a new BVH loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * Whether to animate bone positions or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.animateBonePositions = true;

		/**
		 * Whether to animate bone rotations or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.animateBoneRotations = true;

	}

	/**
	 * Starts loading from the given URL and passes the loaded BVH asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({skeleton:Skeleton,clip:AnimationClip})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Parses the given BVH data and returns the resulting data.
	 *
	 * @param {string} text - The raw BVH data as a string.
	 * @return {{skeleton:Skeleton,clip:AnimationClip}} An object representing the parsed asset.
	 */
	parse( text ) {

		// reads a string array (lines) from a BVH file
		// and outputs a skeleton structure including motion data

		// returns thee root node:
		// { name: '', channels: [], children: [] }
		function readBvh( lines ) {

			// read model structure

			if ( nextLine( lines ) !== 'HIERARCHY' ) {

				console.error( 'THREE.BVHLoader: HIERARCHY expected.' );

			}

			const list = []; // collects flat array of all bones
			const root = readNode( lines, nextLine( lines ), list );

			// read motion data

			if ( nextLine( lines ) !== 'MOTION' ) {

				console.error( 'THREE.BVHLoader: MOTION expected.' );

			}

			// number of frames

			let tokens = nextLine( lines ).split( /[\s]+/ );
			const numFrames = parseInt( tokens[ 1 ] );

			if ( isNaN( numFrames ) ) {

				console.error( 'THREE.BVHLoader: Failed to read number of frames.' );

			}

			// frame time

			tokens = nextLine( lines ).split( /[\s]+/ );
			const frameTime = parseFloat( tokens[ 2 ] );

			if ( isNaN( frameTime ) ) {

				console.error( 'THREE.BVHLoader: Failed to read frame time.' );

			}

			// read frame data line by line

			for ( let i = 0; i < numFrames; i ++ ) {

				tokens = nextLine( lines ).split( /[\s]+/ );
				readFrameData( tokens, i * frameTime, root );

			}

			return list;

		}

		/*
			Recursively reads data from a single frame into the bone hierarchy.
			The passed bone hierarchy has to be structured in the same order as the BVH file.
			keyframe data is stored in bone.frames.

			- data: splitted string array (frame values), values are shift()ed so
			this should be empty after parsing the whole hierarchy.
			- frameTime: playback time for this keyframe.
			- bone: the bone to read frame data from.
		*/
		function readFrameData( data, frameTime, bone ) {

			// end sites have no motion data

			if ( bone.type === 'ENDSITE' ) return;

			// add keyframe

			const keyframe = {
				time: frameTime,
				position: new Vector3(),
				rotation: new Quaternion()
			};

			bone.frames.push( keyframe );

			const quat = new Quaternion();

			const vx = new Vector3( 1, 0, 0 );
			const vy = new Vector3( 0, 1, 0 );
			const vz = new Vector3( 0, 0, 1 );

			// parse values for each channel in node

			for ( let i = 0; i < bone.channels.length; i ++ ) {

				switch ( bone.channels[ i ] ) {

					case 'Xposition':
						keyframe.position.x = parseFloat( data.shift().trim() );
						break;
					case 'Yposition':
						keyframe.position.y = parseFloat( data.shift().trim() );
						break;
					case 'Zposition':
						keyframe.position.z = parseFloat( data.shift().trim() );
						break;
					case 'Xrotation':
						quat.setFromAxisAngle( vx, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					case 'Yrotation':
						quat.setFromAxisAngle( vy, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					case 'Zrotation':
						quat.setFromAxisAngle( vz, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					default:
						console.warn( 'THREE.BVHLoader: Invalid channel type.' );

				}

			}

			// parse child nodes

			for ( let i = 0; i < bone.children.length; i ++ ) {

				readFrameData( data, frameTime, bone.children[ i ] );

			}

		}

		/*
		 Recursively parses the HIERARCHY section of the BVH file

		 - lines: all lines of the file. lines are consumed as we go along.
		 - firstline: line containing the node type and name e.g. 'JOINT hip'
		 - list: collects a flat list of nodes

		 returns: a BVH node including children
		*/
		function readNode( lines, firstline, list ) {

			const node = { name: '', type: '', frames: [] };
			list.push( node );

			// parse node type and name

			let tokens = firstline.split( /[\s]+/ );

			if ( tokens[ 0 ].toUpperCase() === 'END' && tokens[ 1 ].toUpperCase() === 'SITE' ) {

				node.type = 'ENDSITE';
				node.name = 'ENDSITE'; // bvh end sites have no name

			} else {

				node.name = tokens[ 1 ];
				node.type = tokens[ 0 ].toUpperCase();

			}

			if ( nextLine( lines ) !== '{' ) {

				console.error( 'THREE.BVHLoader: Expected opening { after type & name' );

			}

			// parse OFFSET

			tokens = nextLine( lines ).split( /[\s]+/ );

			if ( tokens[ 0 ] !== 'OFFSET' ) {

				console.error( 'THREE.BVHLoader: Expected OFFSET but got: ' + tokens[ 0 ] );

			}

			if ( tokens.length !== 4 ) {

				console.error( 'THREE.BVHLoader: Invalid number of values for OFFSET.' );

			}

			const offset = new Vector3(
				parseFloat( tokens[ 1 ] ),
				parseFloat( tokens[ 2 ] ),
				parseFloat( tokens[ 3 ] )
			);

			if ( isNaN( offset.x ) || isNaN( offset.y ) || isNaN( offset.z ) ) {

				console.error( 'THREE.BVHLoader: Invalid values of OFFSET.' );

			}

			node.offset = offset;

			// parse CHANNELS definitions

			if ( node.type !== 'ENDSITE' ) {

				tokens = nextLine( lines ).split( /[\s]+/ );

				if ( tokens[ 0 ] !== 'CHANNELS' ) {

					console.error( 'THREE.BVHLoader: Expected CHANNELS definition.' );

				}

				const numChannels = parseInt( tokens[ 1 ] );
				node.channels = tokens.splice( 2, numChannels );
				node.children = [];

			}

			// read children

			while ( true ) {

				const line = nextLine( lines );

				if ( line === '}' ) {

					return node;

				} else {

					node.children.push( readNode( lines, line, list ) );

				}

			}

		}

		/*
			recursively converts the internal bvh node structure to a Bone hierarchy

			source: the bvh root node
			list: pass an empty array, collects a flat list of all converted THREE.Bones

			returns the root Bone
		*/
		function toTHREEBone( source, list ) {

			const bone = new Bone();
			list.push( bone );

			bone.position.add( source.offset );
			bone.name = source.name;

			if ( source.type !== 'ENDSITE' ) {

				for ( let i = 0; i < source.children.length; i ++ ) {

					bone.add( toTHREEBone( source.children[ i ], list ) );

				}

			}

			return bone;

		}

		/*
			builds an AnimationClip from the keyframe data saved in each bone.

			bone: bvh root node

			returns: an AnimationClip containing position and quaternion tracks
		*/
		function toTHREEAnimation( bones ) {

			const tracks = [];

			// create a position and quaternion animation track for each node

			for ( let i = 0; i < bones.length; i ++ ) {

				const bone = bones[ i ];

				if ( bone.type === 'ENDSITE' )
					continue;

				// track data

				const times = [];
				const positions = [];
				const rotations = [];

				for ( let j = 0; j < bone.frames.length; j ++ ) {

					const frame = bone.frames[ j ];

					times.push( frame.time );

					// the animation system animates the position property,
					// so we have to add the joint offset to all values

					positions.push( frame.position.x + bone.offset.x );
					positions.push( frame.position.y + bone.offset.y );
					positions.push( frame.position.z + bone.offset.z );

					rotations.push( frame.rotation.x );
					rotations.push( frame.rotation.y );
					rotations.push( frame.rotation.z );
					rotations.push( frame.rotation.w );

				}

				if ( scope.animateBonePositions ) {

					tracks.push( new VectorKeyframeTrack( bone.name + '.position', times, positions ) );

				}

				if ( scope.animateBoneRotations ) {

					tracks.push( new QuaternionKeyframeTrack( bone.name + '.quaternion', times, rotations ) );

				}

			}

			return new AnimationClip( 'animation', - 1, tracks );

		}

		/*
			returns the next non-empty line in lines
		*/
		function nextLine( lines ) {

			let line;
			// skip empty lines
			while ( ( line = lines.shift().trim() ).length === 0 ) { }

			return line;

		}

		const scope = this;

		const lines = text.split( /[\r\n]+/g );

		const bones = readBvh( lines );

		const threeBones = [];
		toTHREEBone( bones[ 0 ], threeBones );

		const threeClip = toTHREEAnimation( bones );

		return {
			skeleton: new Skeleton( threeBones ),
			clip: threeClip
		};

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: { skeleton: Skeleton; clip: AnimationClip; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `parse(text: string): { skeleton: Skeleton; clip: AnimationClip; }`

<details><summary>Code</summary>

```ts
parse( text ) {

		// reads a string array (lines) from a BVH file
		// and outputs a skeleton structure including motion data

		// returns thee root node:
		// { name: '', channels: [], children: [] }
		function readBvh( lines ) {

			// read model structure

			if ( nextLine( lines ) !== 'HIERARCHY' ) {

				console.error( 'THREE.BVHLoader: HIERARCHY expected.' );

			}

			const list = []; // collects flat array of all bones
			const root = readNode( lines, nextLine( lines ), list );

			// read motion data

			if ( nextLine( lines ) !== 'MOTION' ) {

				console.error( 'THREE.BVHLoader: MOTION expected.' );

			}

			// number of frames

			let tokens = nextLine( lines ).split( /[\s]+/ );
			const numFrames = parseInt( tokens[ 1 ] );

			if ( isNaN( numFrames ) ) {

				console.error( 'THREE.BVHLoader: Failed to read number of frames.' );

			}

			// frame time

			tokens = nextLine( lines ).split( /[\s]+/ );
			const frameTime = parseFloat( tokens[ 2 ] );

			if ( isNaN( frameTime ) ) {

				console.error( 'THREE.BVHLoader: Failed to read frame time.' );

			}

			// read frame data line by line

			for ( let i = 0; i < numFrames; i ++ ) {

				tokens = nextLine( lines ).split( /[\s]+/ );
				readFrameData( tokens, i * frameTime, root );

			}

			return list;

		}

		/*
			Recursively reads data from a single frame into the bone hierarchy.
			The passed bone hierarchy has to be structured in the same order as the BVH file.
			keyframe data is stored in bone.frames.

			- data: splitted string array (frame values), values are shift()ed so
			this should be empty after parsing the whole hierarchy.
			- frameTime: playback time for this keyframe.
			- bone: the bone to read frame data from.
		*/
		function readFrameData( data, frameTime, bone ) {

			// end sites have no motion data

			if ( bone.type === 'ENDSITE' ) return;

			// add keyframe

			const keyframe = {
				time: frameTime,
				position: new Vector3(),
				rotation: new Quaternion()
			};

			bone.frames.push( keyframe );

			const quat = new Quaternion();

			const vx = new Vector3( 1, 0, 0 );
			const vy = new Vector3( 0, 1, 0 );
			const vz = new Vector3( 0, 0, 1 );

			// parse values for each channel in node

			for ( let i = 0; i < bone.channels.length; i ++ ) {

				switch ( bone.channels[ i ] ) {

					case 'Xposition':
						keyframe.position.x = parseFloat( data.shift().trim() );
						break;
					case 'Yposition':
						keyframe.position.y = parseFloat( data.shift().trim() );
						break;
					case 'Zposition':
						keyframe.position.z = parseFloat( data.shift().trim() );
						break;
					case 'Xrotation':
						quat.setFromAxisAngle( vx, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					case 'Yrotation':
						quat.setFromAxisAngle( vy, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					case 'Zrotation':
						quat.setFromAxisAngle( vz, parseFloat( data.shift().trim() ) * Math.PI / 180 );
						keyframe.rotation.multiply( quat );
						break;
					default:
						console.warn( 'THREE.BVHLoader: Invalid channel type.' );

				}

			}

			// parse child nodes

			for ( let i = 0; i < bone.children.length; i ++ ) {

				readFrameData( data, frameTime, bone.children[ i ] );

			}

		}

		/*
		 Recursively parses the HIERARCHY section of the BVH file

		 - lines: all lines of the file. lines are consumed as we go along.
		 - firstline: line containing the node type and name e.g. 'JOINT hip'
		 - list: collects a flat list of nodes

		 returns: a BVH node including children
		*/
		function readNode( lines, firstline, list ) {

			const node = { name: '', type: '', frames: [] };
			list.push( node );

			// parse node type and name

			let tokens = firstline.split( /[\s]+/ );

			if ( tokens[ 0 ].toUpperCase() === 'END' && tokens[ 1 ].toUpperCase() === 'SITE' ) {

				node.type = 'ENDSITE';
				node.name = 'ENDSITE'; // bvh end sites have no name

			} else {

				node.name = tokens[ 1 ];
				node.type = tokens[ 0 ].toUpperCase();

			}

			if ( nextLine( lines ) !== '{' ) {

				console.error( 'THREE.BVHLoader: Expected opening { after type & name' );

			}

			// parse OFFSET

			tokens = nextLine( lines ).split( /[\s]+/ );

			if ( tokens[ 0 ] !== 'OFFSET' ) {

				console.error( 'THREE.BVHLoader: Expected OFFSET but got: ' + tokens[ 0 ] );

			}

			if ( tokens.length !== 4 ) {

				console.error( 'THREE.BVHLoader: Invalid number of values for OFFSET.' );

			}

			const offset = new Vector3(
				parseFloat( tokens[ 1 ] ),
				parseFloat( tokens[ 2 ] ),
				parseFloat( tokens[ 3 ] )
			);

			if ( isNaN( offset.x ) || isNaN( offset.y ) || isNaN( offset.z ) ) {

				console.error( 'THREE.BVHLoader: Invalid values of OFFSET.' );

			}

			node.offset = offset;

			// parse CHANNELS definitions

			if ( node.type !== 'ENDSITE' ) {

				tokens = nextLine( lines ).split( /[\s]+/ );

				if ( tokens[ 0 ] !== 'CHANNELS' ) {

					console.error( 'THREE.BVHLoader: Expected CHANNELS definition.' );

				}

				const numChannels = parseInt( tokens[ 1 ] );
				node.channels = tokens.splice( 2, numChannels );
				node.children = [];

			}

			// read children

			while ( true ) {

				const line = nextLine( lines );

				if ( line === '}' ) {

					return node;

				} else {

					node.children.push( readNode( lines, line, list ) );

				}

			}

		}

		/*
			recursively converts the internal bvh node structure to a Bone hierarchy

			source: the bvh root node
			list: pass an empty array, collects a flat list of all converted THREE.Bones

			returns the root Bone
		*/
		function toTHREEBone( source, list ) {

			const bone = new Bone();
			list.push( bone );

			bone.position.add( source.offset );
			bone.name = source.name;

			if ( source.type !== 'ENDSITE' ) {

				for ( let i = 0; i < source.children.length; i ++ ) {

					bone.add( toTHREEBone( source.children[ i ], list ) );

				}

			}

			return bone;

		}

		/*
			builds an AnimationClip from the keyframe data saved in each bone.

			bone: bvh root node

			returns: an AnimationClip containing position and quaternion tracks
		*/
		function toTHREEAnimation( bones ) {

			const tracks = [];

			// create a position and quaternion animation track for each node

			for ( let i = 0; i < bones.length; i ++ ) {

				const bone = bones[ i ];

				if ( bone.type === 'ENDSITE' )
					continue;

				// track data

				const times = [];
				const positions = [];
				const rotations = [];

				for ( let j = 0; j < bone.frames.length; j ++ ) {

					const frame = bone.frames[ j ];

					times.push( frame.time );

					// the animation system animates the position property,
					// so we have to add the joint offset to all values

					positions.push( frame.position.x + bone.offset.x );
					positions.push( frame.position.y + bone.offset.y );
					positions.push( frame.position.z + bone.offset.z );

					rotations.push( frame.rotation.x );
					rotations.push( frame.rotation.y );
					rotations.push( frame.rotation.z );
					rotations.push( frame.rotation.w );

				}

				if ( scope.animateBonePositions ) {

					tracks.push( new VectorKeyframeTrack( bone.name + '.position', times, positions ) );

				}

				if ( scope.animateBoneRotations ) {

					tracks.push( new QuaternionKeyframeTrack( bone.name + '.quaternion', times, rotations ) );

				}

			}

			return new AnimationClip( 'animation', - 1, tracks );

		}

		/*
			returns the next non-empty line in lines
		*/
		function nextLine( lines ) {

			let line;
			// skip empty lines
			while ( ( line = lines.shift().trim() ).length === 0 ) { }

			return line;

		}

		const scope = this;

		const lines = text.split( /[\r\n]+/g );

		const bones = readBvh( lines );

		const threeBones = [];
		toTHREEBone( bones[ 0 ], threeBones );

		const threeClip = toTHREEAnimation( bones );

		return {
			skeleton: new Skeleton( threeBones ),
			clip: threeClip
		};

	}
```
</details>


---