        # Tooling Fundamentals

        ## Vite vs Webpack (why Vite is faster)

        ### What they are
        Bundlers and dev servers that:
        - Process JS/TS
        - Resolve imports
        - Handle CSS/assets
        - Produce build output

        ### Webpack
        - Bundles entire app on start and rebundles on change
        - **Drawbacks:**
            - Slow startup
            - Slow HMR on large apps (Hot Module Replacement: updating code without full page reload)
            - Heavy configuration

        ### Vite
        - No bundling during development
        - Uses native ES modules; browser handles imports
        - Only bundles for production
        - **Process:**
            - Browser requests modules as needed
            - Only changed files reload
        - **Advantages:** Minimal work, native browser behavior
        - Uses Rollup for production builds (optimized bundler for ES modules with excellent tree-shaking)

        ## ESLint Rules (not just "fix on save")

        ### Purpose
        Static code analyzer (not a formatter) that:
        - Finds bugs
        - Enforces patterns
        - Protects correctness

        ### Examples
        - Suggests `let` instead of `const`
        - Detects missing dependencies in useEffect
        - Flags assignments in conditions

        ### Benefits
        - Enforces team standards
        - Ensures React correctness
        - Improves accessibility and performance

        ### Key Difference
        ESLint cares about code meaning; Prettier handles aesthetics

        ## npm vs pnpm vs yarn

        ### Common Features
        All download dependencies, resolve versions, manage lock files, and run scripts

        ### npm
        - Included with Node
        - Simple, but slower installs and large node_modules

        ### Yarn
        - Faster than old npm
        - Better lockfile
        - Widely adopted

        ### pnpm
        - Content-addressable store
        - Packages stored once globally; projects reference via symlinks
        - Faster installs, smaller disk usage, stricter dependency resolution
        - Fewer "works on my machine" bugs

        ## Build Output (what goes into dist/)

        ### Contents
        - Bundled JS
        - Minified CSS
        - Optimized assets
        - Hashed filenames (for cache busting and safe long-term caching)

        ### Build Process
        - **Tree shaking:** Remove unused exports from ES modules
        - **Dead code removal:** Remove unreachable code
        - **Minification:** Reduce code size without changing behavior
        - **Code splitting:** Break app into multiple bundles loaded on demand

        ### Cache Busting
        - Browsers cache code aggressively
        - Hashed filenames change when content updates
        - Browser fetches new files instead of serving stale cache

