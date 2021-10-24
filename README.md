# Custom CRA



1.  npm i react-app-rewired customize-cra add babel-plugin-import less less-loader@^7.3.0
2.  Создать config-overrides.js в корневой директории. Вставить этот код

-----------
    const { override, fixBabelImports, addLessLoader } = require('customize-cra');

    module.exports = override(
        fixBabelImports('import', {
            libraryName: 'antd',
            libraryDirectory: 'es',
            style: true,
        }),
        addLessLoader({
            lessOptions: {
                javascriptEnabled: true,
                modifyVars: {
                    "@primary-color": "#29625f",  //  тут меняешь стили
                }
            }
        }),
    );
------------

3. Изменить start в package.json "start": "react-app-rewired start", 

