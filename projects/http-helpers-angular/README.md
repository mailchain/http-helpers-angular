# HttpHelpers

This package is an Angular service that helps set httpOptions for headers and queryParams. It is helpful for calls to the Mailchain API.

## Installing

```sh
npm install @mailchain/http-helpers-angular --save
```

## Usage

In an Angular service file, eg. `my-service.service.ts`, add the following:

``` ts
  // import the service
  import { HttpHelpersAngularService } from '@mailchain/http-helpers-angular';

  // add to constructor
  constructor(
    private httpHelpersService: HttpHelpersAngularService,
  ) { }

  // add to function, e.g. calling Mailchain api /messages local endpoint:
  myFunction() {
    const protocol = "ethereum" // change accordingly or use function params
    const network = "mainnet" // change accordingly or use function params
    const url = "http://127.0.0.1/messages" // change accordingly or use function params
    const body = outboundMail
    const httpOptions = this.httpHelpersService.getHttpOptions([
      ['protocol', protocol],
      ['network', network]
    ])

    return this.http.post(url, body, httpOptions);
  }

```

---

This library was generated with [Angular CLI](https://github.com/angular/angular-cli) version 8.2.14.

## Code scaffolding

Run `ng generate component component-name --project http-helpers-angular` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module --project http-helpers-angular`.
> Note: Don't forget to add `--project http-helpers-angular` or else it will be added to the default project in your `angular.json` file. 

## Build

Run `ng build http-helpers-angular` to build the project. The build artifacts will be stored in the `dist/` directory.

## Publishing

After building your library with `ng build http-helpers-angular`, go to the dist folder `cd dist/http-helpers-angular` and run `npm publish`.

## Running unit tests

Run `ng test http-helpers-angular` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
