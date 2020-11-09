  Introduction<br>
Spurtcommerce  is B2C and B2B open source eCommerce application, built on the Node.js and Angular and has community edition. I have used this community edition in my commercial projects and it was sufficient to run fully middle level eCommerce application. The attractive feature is modern UI, easy to customize, and full source control. The one of the community edition limitation is that it does not provide multilevel menu support. However, we can easily modify and extend the existing features as they provide full source code. Backend can be replaced with other framework as the application is separated to layers(UI -SPA). The community edition consists of admin (frontend for admin), api (backend server), and store (frontend) folders.      

![alt text](https://github.com/Mirambek/-SpurCommerceCodeAnalysis/blob/master/spurcommerceArchitecture.png?raw=true)

	Store frontend
  <br>
In this article, store frontend folder is analyzed.  As for August  2020, Store front end web site has been implemented in Angular framework 7.0.4,state management NgRx 7.2, and other interesting libraries. Main folders are assets,core,default,environment. “assets” folder contains resources: images,fonts, and config files. “core” folder contains application models,services, and important state management utilization codes. “default” folder contains ui components.

![alt text](https://github.com/Mirambek/-SpurCommerceCodeAnalysis/blob/master/frontend.png?raw=true)

The core folder – NgRx, effects.
<br>
The core folder implements all ngrx,effects, and sandbox pattern configuration and services except UI part(component). It is organized based on application UI feature. It has additional models, shared, and provider folders. The following picture dipicts how the ngrx, effects, and sandbox pattern are interrelated in spurcommerce. 

![alt text](https://github.com/Mirambek/-SpurCommerceCodeAnalysis/blob/master/ngrx.png?raw=true)

UI folder - Components
<br>
In the default folder, ui components are structured in the conventional way of Angular application. It contains only UI part of application. It has common,pages,shared,and theme folders. Pages folder are divided into the feature based modules. Every feature module registers own dedicated sandbox services. Key properties are bound to selectors and events are bound to the methods of sandbox services. More about sandbox pattern can be found at https://blog.strongbrew.io/A-scalable-angular-architecture-part2/. 
