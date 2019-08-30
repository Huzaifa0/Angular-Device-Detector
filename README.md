# Angular-Device-Detector
Angular Device Detector An Angular2+ library to detect the device, OS and browser details.An Angular 2 (and beyond) powered AOT compatible device detector that helps to identify browser, os and other useful information regarding the device using the app. The processing is based on user-agent.  Installation To install this library, run:  $ npm install ngx-device-detector –save Usage Import DeviceDetectorModule in your app.module.ts    import { NgModule } from ‘@angular/core‘;   import { DeviceDetectorModule } from ‘ngx-device-detector‘;   …   @NgModule({     declarations: [       …       LoginComponent,       SignupComponent       …     ],     imports: [       CommonModule,       FormsModule,       DeviceDetectorModule.forRoot()     ],     providers:[       AuthService     ]     …   }) In your component where you want to use the Device Service    import { Component } from ‘@angular/core‘;   …   import { DeviceDetectorService } from ‘ngx-device-detector‘;   …   @Component({     selector: ‘home‘,  // &lt;home>&lt;/home>     styleUrls: [ ‘./home.component.scss‘ ],     templateUrl: ‘./home.component.html‘,     …   })     export class HomeComponent {     deviceInfo = null;     …     constructor(…, private http: Http, private deviceService: DeviceDetectorService) {       this.epicFunction();     }     …     epicFunction() {       console.log(‘hello `Home` component‘);       this.deviceInfo = this.deviceService.getDeviceInfo();       const isMobile = this.deviceService.isMobile();       const isTablet = this.deviceService.isTablet();       const isDesktopDevice = this.deviceService.isDesktop();       console.log(this.deviceInfo);       console.log(isMobile);  // returns if the device is a mobile device (android / iPhone / windows-phone etc)       console.log(isTablet);  // returns if the device us a tablet (iPad etc)       console.log(isDesktopDevice); // returns if the app is running on a Desktop browser.     }     …   }
