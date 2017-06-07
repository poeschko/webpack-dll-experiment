# Webpack DLL Experiment

## Setup

    npm install

## Build

    npm run build

## Experiment

1. Build
    1. Note the output file name: dll-user/js/output-1f59ed4c2eedc906e0d5.js
    2. Note that it references `beta_3ff31ff94881a98ceb9c`
2. In  dll/beta.js, change the string `"beta"` to `"gama"`
3. Build
    1. Note the output file name is still dll-user/js/output-1f59ed4c2eedc906e0d5.js
    2. But it now references `beta_013fee3ee71cd6a0f141`

## Conclusion

The contents of a build artifact change (due to `DllReferencePlugin` referencing a different DLL name) without the output file name (based on `[chunkhash]`) changing.
