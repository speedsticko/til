Typescript adds types to JavaScript.

To use it you need the tsc (TypeScript Compiler) and a tsconfig.json configuration file to control compiler options (command line arguments can be used as well).

The DefinitelyTyped repo contains high quality type annotations for popular libraries in the "@types" organization that can be referenced by TypeScript automatically as long as it's in your package.json.

The most trouble I had with TypeScript was using it with legacy non-module written JavaScript like jQuery, jQuery plugins, and custom code that depended on things being dynamically added to the global (window) context. 
In the interest of time I fixed the compiler errors by marking types as "any" and using Interfaces and Declaration Merging to tell the compiler about the unknown types.

Combining TypeScript with WebPack
- I couldn't get this going since our legacy code was not using modules
- There's a ProvidePlugin that is supposed to help with non-module Javascript but it didn't seem to work and make TypeScript happy at the same time (even using a "declar var" vs an "import $" to not create a new module)
- Also the webpack.config.js needed to be in the same folder as the package.json for it to locate the modules like "webpack" for the ProvidePlugin
- Enaling the NODE_DEBUG=module environment variable helped a lot in troubleshooting
- Abandoned this approach for Gulp to minimize and concat our legacy code

Combining TypeScript with Gulp
- A lot more straight-forward to get working than WebPack, just require some plugins and pipe them through: gulp-typescript, gulp-uglify, gulp-concat, gulp-sourcemaps
- only tricky part was merging the TypeScript files which needed to be compiled to JS first and the existing 3rd party JS like jQuery, jQuery UI

