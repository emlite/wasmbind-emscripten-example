# wasmbind-example

This is an example C++ repo which shows how you can use wasmbind to target web API via emscripten, wasmbind and emlite.

wasmbind is fetched in the CMake script using FetchContent.

Do note that using npm is not strictly necessary, however it simplifies bundling emlite and managing its version.

## Usage
After git cloning the repo:
```bash
npm i
npm run cmake:config
npm run cmake:build
npm run pack
npm run serve
```

The contents of these commands can be found in the package.json scripts entry.

