## Error logs

### npm start

	dyo@dyo-medio:~/sites_ng/ng2_setup$ npm start

	> angular2-quickstart@1.0.0 start /home/dyo/sites_ng/ng2_setup
	> tsc && concurrently "npm run tsc:w" "npm run lite" 

	node_modules/@angular/compiler/src/compile_metadata.d.ts(345,20): error TS2304: Cannot find name 'Set'.
	node_modules/@angular/compiler/src/compile_metadata.d.ts(346,15): error TS2304: Cannot find name 'Set'.
	node_modules/@angular/compiler/src/directive_normalizer.d.ts(19,100): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/compiler/src/directive_normalizer.d.ts(21,74): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/compiler/src/offline_compiler.d.ts(15,26): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/compiler/src/offline_compiler.d.ts(16,38): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/compiler/src/offline_compiler.d.ts(31,124): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/compiler/src/output/output_ast.d.ts(424,63): error TS2304: Cannot find name 'Set'.
	node_modules/@angular/compiler/src/resource_loader.d.ts(13,23): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/compiler/src/runtime_compiler.d.ts(40,49): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/compiler/src/runtime_compiler.d.ts(42,65): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/compiler/src/template_parser/template_parser.d.ts(45,12): error TS2304: Cannot find name 'Set'.
	node_modules/@angular/compiler/src/util.d.ts(35,18): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/compiler/src/util.d.ts(36,46): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/compiler/src/view_compiler/compile_element.d.ts(33,16): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/compiler/src/view_compiler/compile_query.d.ts(24,49): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/compiler/src/view_compiler/compile_view.d.ts(29,18): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/compiler/src/view_compiler/compile_view.d.ts(51,16): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/compiler/src/view_compiler/compile_view.d.ts(53,13): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/application_init.d.ts(16,18): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/core/src/application_ref.d.ts(106,67): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/core/src/application_ref.d.ts(122,101): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/core/src/application_ref.d.ts(148,67): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/core/src/application_ref.d.ts(150,101): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/core/src/change_detection/differs/default_keyvalue_differ.d.ts(24,15): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/change_detection/differs/default_keyvalue_differ.d.ts(28,16): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/di/reflective_provider.d.ts(88,123): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/di/reflective_provider.d.ts(88,165): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(2,25): error TS2304: Cannot find name 'MapConstructor'.
	node_modules/@angular/core/src/facade/collection.d.ts(3,25): error TS2304: Cannot find name 'SetConstructor'.
	node_modules/@angular/core/src/facade/collection.d.ts(5,27): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(5,39): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(8,9): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(9,30): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(12,43): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(13,27): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(15,23): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(16,25): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/collection.d.ts(101,41): error TS2304: Cannot find name 'Set'.
	node_modules/@angular/core/src/facade/collection.d.ts(102,22): error TS2304: Cannot find name 'Set'.
	node_modules/@angular/core/src/facade/collection.d.ts(103,25): error TS2304: Cannot find name 'Set'.
	node_modules/@angular/core/src/facade/lang.d.ts(12,17): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/facade/lang.d.ts(13,17): error TS2304: Cannot find name 'Set'.
	node_modules/@angular/core/src/facade/lang.d.ts(51,59): error TS2304: Cannot find name 'Map'.
	node_modules/@angular/core/src/linker/compiler.d.ts(53,49): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/core/src/linker/compiler.d.ts(61,65): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/core/src/linker/ng_module_factory_loader.d.ts(14,34): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/core/src/linker/system_js_ng_module_factory_loader.d.ts(28,25): error TS2304: Cannot find name 'Promise'.
	node_modules/@angular/platform-browser-dynamic/src/resource_loader/resource_loader_impl.d.ts(10,23): error TS2304: Cannot find name 'Promise'.
	node_modules/rxjs/Observable.d.ts(10,66): error TS2304: Cannot find name 'Promise'.
	node_modules/rxjs/Observable.d.ts(66,60): error TS2304: Cannot find name 'Promise'.
	node_modules/rxjs/Observable.d.ts(66,70): error TS2304: Cannot find name 'Promise'.
	app/main.ts(2,27): error TS2307: Cannot find module './app.module'.

	npm ERR! Linux 3.16.0-30-generic
	npm ERR! argv "/usr/local/bin/node" "/usr/local/bin/npm" "start"
	npm ERR! node v5.6.0
	npm ERR! npm  v3.6.0
	npm ERR! code ELIFECYCLE
	npm ERR! angular2-quickstart@1.0.0 start: `tsc && concurrently "npm run tsc:w" "npm run lite" `
	npm ERR! Exit status 2
	npm ERR! 
	npm ERR! Failed at the angular2-quickstart@1.0.0 start script 'tsc && concurrently "npm run tsc:w" "npm run lite" '.
	npm ERR! Make sure you have the latest version of node.js and npm installed.
	npm ERR! If you do, this is most likely a problem with the angular2-quickstart package,
	npm ERR! not with npm itself.
	npm ERR! Tell the author that this fails on your system:
	npm ERR!     tsc && concurrently "npm run tsc:w" "npm run lite" 
	npm ERR! You can get information on how to open an issue for this project with:
	npm ERR!     npm bugs angular2-quickstart
	npm ERR! Or if that isn't available, you can get their info via:
	npm ERR!     npm owner ls angular2-quickstart
	npm ERR! There is likely additional logging output above.

	npm ERR! Please include the following file with any support request:
	npm ERR!     /home/dyo/sites_ng/ng2_setup/npm-debug.log

Solution 
	
+ Update npm
+ Or run npm run tsc:w and npm run lite
+ Or Just follow quick as it is.
	
### Can not update on server

main.ts add this lines:

	import {enableProdMode} from '@angular/core';

	enableProdMode();