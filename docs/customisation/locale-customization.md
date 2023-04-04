# Locale Customization

## Steps to support a new language

- Under `locales` folder, localization of a particular language json file has to be added.
- Language json has to be imported in `i18n.ts` and load the resources to i18next as follows.
  `import  fil  from  './locales/fil.json';`
  `const  resources  =  {  en, fil,  ar,  hi,  kn,  ta  };`
- To ensure the language needs to be included in const `SUPPORTED_LANGUAGES`.
  `const  {  t  }  =  useTranslation('common');`
- To use with react, must include key with 't' function
  `<Text>{t('editLabel')}</Text>`

## About libraries

1. [i18next](https://www.i18next.com/)
2. [react-i18next](https://react.i18next.com/)
3. [expo-localization](https://docs.expo.dev/versions/latest/sdk/localization/)

* Inji has the capability to support multiple languages.

* `i18next` is an internationalization framework. It provides the standard i18n features such as [plurals](/translation-function/plurals), [context](/translation-function/context), [interpolation](/translation-function/interpolation), [format](/translation-function/formatting). It provides a complete solution to localize product from web to mobile and desktop.

* `react-i18next` is a set of components, hooks, and plugins that sit on top of i18next, and is specifically designed for React.

* `expo-localization` allows you to localize the app, customizing the experience for specific regions, languages. It also provides access to the locale data on the native device.