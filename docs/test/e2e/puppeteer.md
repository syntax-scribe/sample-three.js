[⬅️ Back to Table of Contents](../../index.md)

# 📄 `puppeteer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 37 |
| ⚡ Async/Await Patterns | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`test/e2e/puppeteer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `chalk` | `chalk` |
| `puppeteer` | `puppeteer` |
| `express` | `express` |
| `path` | `path` |
| `pixelmatch` | `pixelmatch` |
| `Jimp` | `jimp` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `idleTime` | `12` | let/var | `12` | ✗ |
| `parseTime` | `6` | let/var | `6` | ✗ |
| `exceptionList` | `string[]` | let/var | `[ // tiles not loaded in time for screenshot 'webgl_loader_3dtiles', // video...` | ✗ |
| `port` | `1234` | let/var | `1234` | ✗ |
| `pixelThreshold` | `0.1` | let/var | `0.1` | ✗ |
| `maxDifferentPixels` | `0.3` | let/var | `0.3` | ✗ |
| `networkTimeout` | `5` | let/var | `5` | ✗ |
| `renderTimeout` | `5` | let/var | `5` | ✗ |
| `numAttempts` | `2` | let/var | `2` | ✗ |
| `numPages` | `8` | let/var | `8` | ✗ |
| `numCIJobs` | `4` | let/var | `4` | ✗ |
| `width` | `400` | let/var | `400` | ✗ |
| `height` | `250` | let/var | `250` | ✗ |
| `viewScale` | `2` | let/var | `2` | ✗ |
| `jpgQuality` | `95` | let/var | `95` | ✗ |
| `browser` | `any` | let/var | `*not shown*` | ✗ |
| `isMakeScreenshot` | `boolean` | let/var | `false` | ✗ |
| `isWebGPU` | `boolean` | let/var | `false` | ✗ |
| `argvIndex` | `number` | let/var | `2` | ✗ |
| `isExactList` | `boolean` | let/var | `exactList.length !== 0` | ✗ |
| `flags` | `string[]` | let/var | `[ '--hide-scrollbars', '--enable-gpu' ]` | ✗ |
| `viewport` | `{ width: number; height: number; }` | let/var | `{ width: width * viewScale, height: height * viewScale }` | ✗ |
| `cleanPage` | `string` | let/var | `await fs.readFile( 'test/e2e/clean-page.js', 'utf8' )` | ✗ |
| `injection` | `string` | let/var | `await fs.readFile( 'test/e2e/deterministic-injection.js', 'utf8' )` | ✗ |
| `builds` | `{ 'three.core.js': any; 'three.module...` | let/var | `{ 'three.core.js': buildInjection( await fs.readFile( 'build/three.core.js', ...` | ✗ |
| `errorMessagesCache` | `any[]` | let/var | `[]` | ✗ |
| `pages` | `any` | let/var | `await browser.pages()` | ✗ |
| `failedScreenshots` | `any[]` | let/var | `[]` | ✗ |
| `queue` | `PromiseQueue` | let/var | `new PromiseQueue( makeAttempt, pages, failedScreenshots, cleanPage, isMakeScr...` | ✗ |
| `file` | `any` | let/var | `page.file` | ✗ |
| `args` | `any[]` | let/var | `await Promise.all( msg.args().map( async arg => { try { return await arg.exec...` | ✗ |
| `page` | `any` | let/var | `await new Promise( ( resolve, reject ) => { const interval = setInterval( () ...` | ✗ |
| `renderTimeoutExceeded` | `boolean` | let/var | `( renderTimeout > 0 ) && ( performance._now() - renderStart > 1000 * renderTi...` | ✗ |
| `expected` | `any` | let/var | `*not shown*` | ✗ |
| `actual` | `any` | let/var | `screenshot.bitmap` | ✗ |
| `numDifferentPixels` | `any` | let/var | `*not shown*` | ✗ |
| `differentPixels` | `number` | let/var | `numDifferentPixels / ( actual.width * actual.height ) * 100` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `main` | fs.rm( 'test/e2e/output-screenshots', { recursive: true, force: true } ), fs.mkdir( 'test/e2e/output-screenshots' ), fs.readdir( 'examples' ), puppeteer.launch( {
		headless: process.env.VISIBLE ? false : 'new',
		args: flags,
		defaultViewport: viewport,
		handleSIGINT: false,
		protocolTimeout: 0
	} ), fs.readFile( 'test/e2e/clean-page.js', 'utf8' ), fs.readFile( 'test/e2e/deterministic-injection.js', 'utf8' ), fs.readFile( 'build/three.core.js', 'utf8' ), fs.readFile( 'build/three.module.js', 'utf8' ), fs.readFile( 'build/three.webgpu.js', 'utf8' ), browser.pages(), browser.newPage(), preparePage( page, injection, builds, errorMessagesCache ), queue.waitForAll() | *none* |
| async-function | `preparePage` | page.evaluateOnNewDocument( injection ), page.setRequestInterception( true ), Promise.all( msg.args().map( async arg => {
			try {
				return await arg.executionContext().evaluate( arg => arg instanceof Error ? arg.message : arg, arg );
			} catch ( e ) { // Execution context might have been already destroyed
				return arg;
			}
		} ) ), arg.executionContext().evaluate( arg => arg instanceof Error ? arg.message : arg, arg ), response.buffer().then( buffer => page.pageSize += buffer.length ), request.respond( {
					status: 200,
					contentType: 'application/javascript; charset=utf-8',
					body: builds[ build ]
				} ), request.continue() | Promise.all, response.buffer().then |
| async-function | `makeAttempt` | new Promise( ( resolve, reject ) => {

		const interval = setInterval( () => {

			for ( const page of pages ) {

				if ( page.file === undefined ) {

					page.file = file; // acquire lock
					clearInterval( interval );
					resolve( page );
					break;

				}

			}

		}, 100 );

	} ), page.goto( `http://localhost:${ port }/examples/${ file }.html`, {
				waitUntil: 'networkidle0',
				timeout: networkTimeout * 60000
			} ), page.evaluate( cleanPage ), page.waitForNetworkIdle( {
				timeout: networkTimeout * 60000,
				idleTime: idleTime * 1000
			} ), page.evaluate( async ( renderTimeout, parseTime ) => {

				await new Promise( resolve => setTimeout( resolve, parseTime ) );

				/* Resolve render promise */

				window._renderStarted = true;

				await new Promise( function ( resolve, reject ) {

					const renderStart = performance._now();

					const waitingLoop = setInterval( function () {

						const renderTimeoutExceeded = ( renderTimeout > 0 ) && ( performance._now() - renderStart > 1000 * renderTimeout );

						if ( renderTimeoutExceeded ) {

							clearInterval( waitingLoop );
							reject( 'Render timeout exceeded' );

						} else if ( window._renderFinished ) {

							clearInterval( waitingLoop );
							resolve();

						}

					}, 10 );

				} );

			}, renderTimeout, page.pageSize / 1024 / 1024 * parseTime * 1000 ), new Promise( resolve => setTimeout( resolve, parseTime ) ), new Promise( function ( resolve, reject ) {

					const renderStart = performance._now();

					const waitingLoop = setInterval( function () {

						const renderTimeoutExceeded = ( renderTimeout > 0 ) && ( performance._now() - renderStart > 1000 * renderTimeout );

						if ( renderTimeoutExceeded ) {

							clearInterval( waitingLoop );
							reject( 'Render timeout exceeded' );

						} else if ( window._renderFinished ) {

							clearInterval( waitingLoop );
							resolve();

						}

					}, 10 );

				} ), Jimp.read( await page.screenshot(), { quality: jpgQuality } ), page.screenshot(), screenshot.write( `examples/screenshots/${ file }.jpg` ), Jimp.read( `examples/screenshots/${ file }.jpg`, { quality: jpgQuality } ), screenshot.write( `test/e2e/output-screenshots/${ file }-actual.jpg` ), screenshot.write( `test/e2e/output-screenshots/${ file }-actual.jpg` ), expected.write( `test/e2e/output-screenshots/${ file }-expected.jpg` ), screenshot.write( `test/e2e/output-screenshots/${ file }-actual.jpg` ), expected.write( `test/e2e/output-screenshots/${ file }-expected.jpg` ), diff.write( `test/e2e/output-screenshots/${ file }-diff.jpg` ) | new Promise(...), new Promise(...), new Promise(...) |


---

## Functions

### `PromiseQueue.add(args: any[]): void`

**Parameters:**

- **`args`** `any[]`

**Returns:** `void`

**Calls:**

- `this.func`
- `this.promises.push`
- `promise.then`
- `this.promises.splice`
- `this.promises.indexOf`

<details><summary>Code</summary>

```typescript
add( ...args ) {

		const promise = this.func( ...args );
		this.promises.push( promise );
		promise.then( () => this.promises.splice( this.promises.indexOf( promise ), 1 ) );

	}
```
</details>

### `PromiseQueue.waitForAll(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `Promise.all`

<details><summary>Code</summary>

```typescript
async waitForAll() {

		while ( this.promises.length > 0 ) {

			await Promise.all( this.promises );

		}

	}
```
</details>

### `main(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `fs.rm`
- `fs.mkdir`
- `process.argv.slice( argvIndex )
		.map`
- `f.replace`
- `( await fs.readdir( 'examples' ) )
		.filter( s => s.slice( - 5 ) === '.html' && s !== 'index.html' )
		.map( s => s.slice( 0, s.length - 5 ) )
		.filter`
- `exactList.includes`
- `exceptionList.includes`
- `files.includes`
- `console.log`
- `files.filter`
- `f.includes`
- `parseInt`
- `files.slice`
- `Math.floor`
- `puppeteer.launch`
- `code.replace`
- `fs.readFile`
- `buildInjection`
- `browser.pages`
- `pages.push`
- `browser.newPage`
- `preparePage`
- `queue.add`
- `queue.waitForAll`
- `failedScreenshots.sort`
- `failedScreenshots.join`
- `console.red`
- `console.green`
- `setTimeout`

**Internal Comments:**
```
/* Create output directory */
/* Find files */ (x2)
/* CI parallelism */
/* Launch browser */ (x2)
// flags.push( '--enable-unsafe-webgpu', '--enable-features=Vulkan', '--use-gl=swiftshader', '--use-angle=swiftshader', '--use-vulkan=swiftshader', '--use-webgpu-adapter=swiftshader' ); (x2)
// if ( process.platform === 'linux' ) flags.push( '--enable-features=Vulkan,UseSkiaRenderer', '--use-vulkan=native', '--disable-vulkan-surface', '--disable-features=VaapiVideoDecoder', '--ignore-gpu-blocklist', '--use-angle=vulkan' ); (x2)
// this line is intended to stop the script if the browser (in headful mode) is closed by user (while debugging) (x2)
// browser.on( 'targetdestroyed', target => ( target.type() === 'other' ) ? close() : null ); (x2)
// for some reason it randomly stops the script after about ~30 screenshots processed (x2)
/* Prepare injections */ (x2)
/* Prepare pages */ (x2)
/* Loop for each file */ (x2)
/* Finish */ (x4)
```

<details><summary>Code</summary>

```typescript
async function main() {

	/* Create output directory */

	try { await fs.rm( 'test/e2e/output-screenshots', { recursive: true, force: true } ); } catch {}
	try { await fs.mkdir( 'test/e2e/output-screenshots' ); } catch {}

	/* Find files */

	let isMakeScreenshot = false;
	let isWebGPU = false;

	let argvIndex = 2;

	if ( process.argv[ argvIndex ] === '--webgpu' ) {

		isWebGPU = true;
		argvIndex ++;

	}

	if ( process.argv[ argvIndex ] === '--make' ) {

		isMakeScreenshot = true;
		argvIndex ++;

	}

	const exactList = process.argv.slice( argvIndex )
		.map( f => f.replace( '.html', '' ) );

	const isExactList = exactList.length !== 0;

	let files = ( await fs.readdir( 'examples' ) )
		.filter( s => s.slice( - 5 ) === '.html' && s !== 'index.html' )
		.map( s => s.slice( 0, s.length - 5 ) )
		.filter( f => isExactList ? exactList.includes( f ) : ! exceptionList.includes( f ) );

	if ( isExactList ) {

		for ( const file of exactList ) {

			if ( ! files.includes( file ) ) {

				console.log( `Warning! Unrecognised example name: ${ file }` );

			}

		}

	}

	if ( isWebGPU ) files = files.filter( f => f.includes( 'webgpu_' ) );

	/* CI parallelism */

	if ( 'CI' in process.env ) {

		const CI = parseInt( process.env.CI );

		files = files.slice(
			Math.floor( CI * files.length / numCIJobs ),
			Math.floor( ( CI + 1 ) * files.length / numCIJobs )
		);

	}

	/* Launch browser */

	const flags = [ '--hide-scrollbars', '--enable-gpu' ];
	// flags.push( '--enable-unsafe-webgpu', '--enable-features=Vulkan', '--use-gl=swiftshader', '--use-angle=swiftshader', '--use-vulkan=swiftshader', '--use-webgpu-adapter=swiftshader' );
	// if ( process.platform === 'linux' ) flags.push( '--enable-features=Vulkan,UseSkiaRenderer', '--use-vulkan=native', '--disable-vulkan-surface', '--disable-features=VaapiVideoDecoder', '--ignore-gpu-blocklist', '--use-angle=vulkan' );

	const viewport = { width: width * viewScale, height: height * viewScale };

	browser = await puppeteer.launch( {
		headless: process.env.VISIBLE ? false : 'new',
		args: flags,
		defaultViewport: viewport,
		handleSIGINT: false,
		protocolTimeout: 0
	} );

	// this line is intended to stop the script if the browser (in headful mode) is closed by user (while debugging)
	// browser.on( 'targetdestroyed', target => ( target.type() === 'other' ) ? close() : null );
	// for some reason it randomly stops the script after about ~30 screenshots processed

	/* Prepare injections */

	const buildInjection = ( code ) => code.replace( /Math\.random\(\) \* 0xffffffff/g, 'Math._random() * 0xffffffff' );

	const cleanPage = await fs.readFile( 'test/e2e/clean-page.js', 'utf8' );
	const injection = await fs.readFile( 'test/e2e/deterministic-injection.js', 'utf8' );

	const builds = {
		'three.core.js': buildInjection( await fs.readFile( 'build/three.core.js', 'utf8' ) ),
		'three.module.js': buildInjection( await fs.readFile( 'build/three.module.js', 'utf8' ) ),
		'three.webgpu.js': buildInjection( await fs.readFile( 'build/three.webgpu.js', 'utf8' ) )
	};

	/* Prepare pages */

	const errorMessagesCache = [];

	const pages = await browser.pages();
	while ( pages.length < numPages && pages.length < files.length ) pages.push( await browser.newPage() );

	for ( const page of pages ) await preparePage( page, injection, builds, errorMessagesCache );

	/* Loop for each file */

	const failedScreenshots = [];

	const queue = new PromiseQueue( makeAttempt, pages, failedScreenshots, cleanPage, isMakeScreenshot );
	for ( const file of files ) queue.add( file );
	await queue.waitForAll();

	/* Finish */

	failedScreenshots.sort();
	const list = failedScreenshots.join( ' ' );

	if ( isMakeScreenshot && failedScreenshots.length ) {

		console.red( 'List of failed screenshots: ' + list );
		console.red( `If you are sure that everything is correct, try to run "npm run make-screenshot ${ list }". If this does not help, try increasing idleTime and parseTime variables in /test/e2e/puppeteer.js file. If this also does not help, add remaining screenshots to the exception list.` );
		console.red( `${ failedScreenshots.length } from ${ files.length } screenshots have not generated successfully.` );

	} else if ( isMakeScreenshot && ! failedScreenshots.length ) {

		console.green( `${ files.length } screenshots successfully generated.` );

	} else if ( failedScreenshots.length ) {

		console.red( 'List of failed screenshots: ' + list );
		console.red( `If you are sure that everything is correct, try to run "npm run make-screenshot ${ list }". If this does not help, try increasing idleTime and parseTime variables in /test/e2e/puppeteer.js file. If this also does not help, add remaining screenshots to the exception list.` );
		console.red( `TEST FAILED! ${ failedScreenshots.length } from ${ files.length } screenshots have not rendered correctly.` );

	} else {

		console.green( `TEST PASSED! ${ files.length } screenshots rendered correctly.` );

	}

	setTimeout( close, 300, failedScreenshots.length );

}
```
</details>

### `buildInjection(code: any): any`

**Parameters:**

- **`code`** `any`

**Returns:** `any`

**Calls:**

- `code.replace`

<details><summary>Code</summary>

```typescript
( code ) => code.replace( /Math\.random\(\) \* 0xffffffff/g, 'Math._random() * 0xffffffff' )
```
</details>

### `preparePage(page: any, injection: any, builds: any, errorMessages: any): Promise<void>`

**Parameters:**

- **`page`** `any`
- **`injection`** `any`
- **`builds`** `any`
- **`errorMessages`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `page.evaluateOnNewDocument`
- `page.setRequestInterception`
- `page.on`
- `msg.type`
- `Promise.all`
- `msg.args().map`
- `arg.executionContext().evaluate`
- `args.join`
- `text.trim`
- `text.replace`
- `text.includes`
- `errorMessages.includes`
- `errorMessages.push`
- `console.yellow`
- `response.buffer().then`
- `request.url`
- `request.respond`
- `request.continue`

**Internal Comments:**
```
/* let page.file, page.pageSize, page.error */ (x2)
```

<details><summary>Code</summary>

```typescript
async function preparePage( page, injection, builds, errorMessages ) {

	/* let page.file, page.pageSize, page.error */

	await page.evaluateOnNewDocument( injection );
	await page.setRequestInterception( true );

	page.on( 'console', async msg => {

		const type = msg.type();

		if ( type !== 'warning' && type !== 'error' ) {

			return;

		}

		const file = page.file;

		if ( file === undefined ) {

			return;

		}

		const args = await Promise.all( msg.args().map( async arg => {
			try {
				return await arg.executionContext().evaluate( arg => arg instanceof Error ? arg.message : arg, arg );
			} catch ( e ) { // Execution context might have been already destroyed
				return arg;
			}
		} ) );

		let text = args.join( ' ' ); // https://github.com/puppeteer/puppeteer/issues/3397#issuecomment-434970058

		text = text.trim();
		if ( text === '' ) return;

		text = file + ': ' + text.replace( /\[\.WebGL-(.+?)\] /g, '' );

		if ( text === `${ file }: JSHandle@error` ) {

			text = `${ file }: Unknown error`;

		}

		if ( text.includes( 'Unable to access the camera/webcam' ) ) {

			return;

		}

		if ( errorMessages.includes( text ) ) {

			return;

		}

		errorMessages.push( text );

		if ( type === 'warning' ) {

			console.yellow( text );

		} else {

			page.error = text;

		}

	} );

	page.on( 'response', async ( response ) => {

		try {

			if ( response.status === 200 ) {

				await response.buffer().then( buffer => page.pageSize += buffer.length );

			}

		} catch {}

	} );

	page.on( 'request', async ( request ) => {

		const url = request.url();

		for ( const build in builds ) {

			if ( url === `http://localhost:${ port }/build/${ build }` ) {

				await request.respond( {
					status: 200,
					contentType: 'application/javascript; charset=utf-8',
					body: builds[ build ]
				} );

				return;

			}

		}

		await request.continue();

	} );

}
```
</details>

### `makeAttempt(pages: any, failedScreenshots: any, cleanPage: any, isMakeScreenshot: any, file: any, attemptID: number): Promise<void>`

**Parameters:**

- **`pages`** `any`
- **`failedScreenshots`** `any`
- **`cleanPage`** `any`
- **`isMakeScreenshot`** `any`
- **`file`** `any`
- **`attemptID`** `number`

**Returns:** `Promise<void>`

**Calls:**

- `setInterval`
- `clearInterval`
- `resolve`
- `page.goto`
- `page.evaluate`
- `page.waitForNetworkIdle`
- `setTimeout`
- `performance._now`
- `reject`
- `e.includes`
- `( await Jimp.read( await page.screenshot(), { quality: jpgQuality } ) ).scale`
- `Jimp.read`
- `page.screenshot`
- `screenshot.write`
- `console.green`
- `screenshot.clone`
- `pixelmatch (from pixelmatch)`
- `expected.write`
- `differentPixels.toFixed`
- `diff.write`
- `console.red`
- `failedScreenshots.push`
- `console.yellow`
- `this.add`

**Internal Comments:**
```
/* Load target page */
/* Render page */ (x2)
/* Resolve render promise */ (x4)
/* Make screenshots */ (x2)
/* Diff screenshots */ (x2)
/* Print results */ (x2)
```

<details><summary>Code</summary>

```typescript
async function makeAttempt( pages, failedScreenshots, cleanPage, isMakeScreenshot, file, attemptID = 0 ) {

	const page = await new Promise( ( resolve, reject ) => {

		const interval = setInterval( () => {

			for ( const page of pages ) {

				if ( page.file === undefined ) {

					page.file = file; // acquire lock
					clearInterval( interval );
					resolve( page );
					break;

				}

			}

		}, 100 );

	} );

	try {

		page.pageSize = 0;
		page.error = undefined;

		/* Load target page */

		try {

			await page.goto( `http://localhost:${ port }/examples/${ file }.html`, {
				waitUntil: 'networkidle0',
				timeout: networkTimeout * 60000
			} );

		} catch ( e ) {

			throw new Error( `Error happened while loading file ${ file }: ${ e }` );

		}

		try {

			/* Render page */

			await page.evaluate( cleanPage );

			await page.waitForNetworkIdle( {
				timeout: networkTimeout * 60000,
				idleTime: idleTime * 1000
			} );

			await page.evaluate( async ( renderTimeout, parseTime ) => {

				await new Promise( resolve => setTimeout( resolve, parseTime ) );

				/* Resolve render promise */

				window._renderStarted = true;

				await new Promise( function ( resolve, reject ) {

					const renderStart = performance._now();

					const waitingLoop = setInterval( function () {

						const renderTimeoutExceeded = ( renderTimeout > 0 ) && ( performance._now() - renderStart > 1000 * renderTimeout );

						if ( renderTimeoutExceeded ) {

							clearInterval( waitingLoop );
							reject( 'Render timeout exceeded' );

						} else if ( window._renderFinished ) {

							clearInterval( waitingLoop );
							resolve();

						}

					}, 10 );

				} );

			}, renderTimeout, page.pageSize / 1024 / 1024 * parseTime * 1000 );

		} catch ( e ) {

			if ( e.includes && e.includes( 'Render timeout exceeded' ) === false ) {

				throw new Error( `Error happened while rendering file ${ file }: ${ e }` );

			} /* else { // This can mean that the example doesn't use requestAnimationFrame loop

				console.yellow( `Render timeout exceeded in file ${ file }` );

			} */ // TODO: fix this

		}

		const screenshot = ( await Jimp.read( await page.screenshot(), { quality: jpgQuality } ) ).scale( 1 / viewScale );

		if ( page.error !== undefined ) throw new Error( page.error );

		if ( isMakeScreenshot ) {

			/* Make screenshots */

			await screenshot.write( `examples/screenshots/${ file }.jpg` );

			console.green( `Screenshot generated for file ${ file }` );

		} else {

			/* Diff screenshots */

			let expected;

			try {

				expected = ( await Jimp.read( `examples/screenshots/${ file }.jpg`, { quality: jpgQuality } ) );

			} catch {

				await screenshot.write( `test/e2e/output-screenshots/${ file }-actual.jpg` );
				throw new Error( `Screenshot does not exist: ${ file }` );

			}

			const actual = screenshot.bitmap;
			const diff = screenshot.clone();

			let numDifferentPixels;

			try {

				numDifferentPixels = pixelmatch( expected.bitmap.data, actual.data, diff.bitmap.data, actual.width, actual.height, {
					threshold: pixelThreshold,
					alpha: 0.2
				} );

			} catch {

				await screenshot.write( `test/e2e/output-screenshots/${ file }-actual.jpg` );
				await expected.write( `test/e2e/output-screenshots/${ file }-expected.jpg` );
				throw new Error( `Image sizes does not match in file: ${ file }` );

			}

			/* Print results */

			const differentPixels = numDifferentPixels / ( actual.width * actual.height ) * 100;

			if ( differentPixels < maxDifferentPixels ) {

				console.green( `Diff ${ differentPixels.toFixed( 1 ) }% in file: ${ file }` );

			} else {

				await screenshot.write( `test/e2e/output-screenshots/${ file }-actual.jpg` );
				await expected.write( `test/e2e/output-screenshots/${ file }-expected.jpg` );
				await diff.write( `test/e2e/output-screenshots/${ file }-diff.jpg` );
				throw new Error( `Diff wrong in ${ differentPixels.toFixed( 1 ) }% of pixels in file: ${ file }` );

			}

		}

	} catch ( e ) {

		if ( attemptID === numAttempts - 1 ) {

			console.red( e );
			failedScreenshots.push( file );

		} else {

			console.yellow( `${ e }, another attempt...` );
			this.add( file, attemptID + 1 );

		}

	}

	page.file = undefined; // release lock

}
```
</details>

### `close(exitCode: number): void`

**Parameters:**

- **`exitCode`** `number`

**Returns:** `void`

**Calls:**

- `console.log`
- `browser.close`
- `server.close`
- `process.exit`

<details><summary>Code</summary>

```typescript
function close( exitCode = 1 ) {

	console.log( 'Closing...' );

	browser.close();
	server.close();
	process.exit( exitCode );

}
```
</details>


---

## Classes

### `PromiseQueue`

<details><summary>Class Code</summary>

```ts
class PromiseQueue {

	constructor( func, ...args ) {

		this.func = func.bind( this, ...args );
		this.promises = [];

	}

	add( ...args ) {

		const promise = this.func( ...args );
		this.promises.push( promise );
		promise.then( () => this.promises.splice( this.promises.indexOf( promise ), 1 ) );

	}

	async waitForAll() {

		while ( this.promises.length > 0 ) {

			await Promise.all( this.promises );

		}

	}

}
```
</details>

#### Methods

##### `add(args: any[]): void`

<details><summary>Code</summary>

```ts
add( ...args ) {

		const promise = this.func( ...args );
		this.promises.push( promise );
		promise.then( () => this.promises.splice( this.promises.indexOf( promise ), 1 ) );

	}
```
</details>

##### `waitForAll(): Promise<void>`

<details><summary>Code</summary>

```ts
async waitForAll() {

		while ( this.promises.length > 0 ) {

			await Promise.all( this.promises );

		}

	}
```
</details>


---