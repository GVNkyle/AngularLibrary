<div align="center">
  <img class="mx-auto center-block d-block" src="https://res.cloudinary.com/khanhvuongnh/image/upload/v1660891556/AngularLibrary/logo_angular_library_cujgix.svg" alt="ngx-spa-utilities-notiflix" width="200" height="200" />
  <h1>ngx-spa-utilities-notiflix</h1> 
</div>


This library was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.0.0.

## Installation

Install `ngx-spa-utilities-notiflix` from `npm`:

```
npm install notiflix ngx-spa-utilities-notiflix
```

Install `ngx-spa-utilities-notiflix` from `yarn`:

```
yarn add notiflix ngx-spa-utilities-notiflix
```

## Setup

[Follow this official page to setup notiflix library](https://github.com/notiflix/Notiflix)

## Usage

```typescript
@Component({
  ...
})
export class AppComponent implements OnInit {
  
  constructor(private notiflixService: NgxNotiflixService) { }

  ngOnInit(): void {
    this.notiflixService.init({
      // Custom OK button
      okButton: 'Okie', 

      // Custom Cancel button
      cancelButton: 'Oh No',

      // Custom loading svg
      loadingSvgUrl: 'assets/img/loading.svg',

      // Custom loading style
      loadingType: 'custom',

      // Custom loading color
      loadingColor: '#ff5549'
    });

    // Fire to show a success notification
    this.notiflixService.success('Hello, World.');
  }
```

### All Functions

```typescript
// Init
init(custom: NotiflixCustom): void

// Notify
success(message: string): void
error(message: string): void
warning(message: string): void
info(message: string): void

// Confirm
confirm(title: string, message: string, okButtonCallback: () => void, cancelButtonCallback?: () => void): void
ask(title: string, question: string, answer: string, okButtonCallback?: () => void, cancelButtonCallback?: () => void): void
prompt(title: string, question: string, defaultAnswer: string, okButtonCallback?: (clientAnswer: string) => void, cancelButtonCallback?: (clientAnswer: string) => void): void

// Loading
showLoading(): void
hideLoading(): void

// Report
successReport(title: string, message: string, callback?: () => void): void
errorReport(title: string, message: string, callback?: () => void): void
warningReport(title: string, message: string, callback?: () => void): void
infoReport(title: string, message: string, callback?: () => void): void

// Block
showBlock(el: string | HTMLElement[] | NodeListOf<HTMLElement>): void
hideBlock(el: string | HTMLElement[] | NodeListOf<HTMLElement>): void
```

### Interfaces

```typescript
export interface NotiflixCustom {
  okButton?: string;
  cancelButton?: string;
  loadingSvgUrl?: string;
  loadingType?: 'standard' | 'hourglass' | 'circle' | 'arrows' | 'dots' | 'pulse' | 'custom';
  loadingColor?: string;
}
```