# Create the product list

### src/app/product-list/product-list.component.html

```ts

<h2>Products</h2>

<div *ngFor="let product of products">
    </div>

````
# add product data

```ts

<h2>Products</h2>

<div *ngFor="let product of products">

    <h3>
        {{ product.name }}
    </h3>

</div>

````
# adding description

```ts
<h2>Products</h2>

<div *ngFor="let product of products">

    <h3>
        <a [title]="product.name + ' details'">
            {{ product.name }}
        </a>
    </h3>

    <p *ngIf="product.description">
        Description: {{ product.description }}
    </p>

</div>

````
# add button

```ts
<h2>Products</h2>

<div *ngFor="let product of products">

    <h3>
        <a [title]="product.name + ' details'">
            {{ product.name }}
        </a>
    </h3>

    <p *ngIf="product.description">
        Description: {{ product.description }}
    </p>

    <button type="button" (click)="share()">
        Share
    </button>

</div>


````
# generate component

```
ng generate component product-alerts

````
The generator creates starter files for the three parts of the component:

- product-alerts.component.ts
- product-alerts.component.html
- product-alerts.component.css

!!! Remove standalone= true && intut=[] and add to app.module !!!

# integrate new component
### src/app/product-alerts/product-alerts.component.ts

```ts
import { Component, Input } from '@angular/core';
import { Product } from '../products';

````

```ts
export class ProductAlertsComponent {

    @Input() product: Product | undefined;

}

````
### src/app/product-alerts/product-alerts.component.html

```ts
<p *ngIf="product && product.price > 700">
<button type="button">Notify Me</button>
</p>

````
# Pass data to a parent component

### src/app/product-alerts/product-alerts.component.ts

```ts
import { Component, Input, Output, EventEmitter } from '@angular/core';
import { Product } from '../products';

````

```ts

export class ProductAlertsComponent {
  @Input() product: Product | undefined;
  @Output() notify = new EventEmitter();
}

````
### src/app/product-alerts/product-alerts.component.html

```ts
<p *ngIf="product && product.price > 700">
  <button type="button" (click)="notify.emit()">Notify Me</button>
</p>

````

### src/app/product-list/product-list.component.ts

```ts
export class ProductListComponent {

  products = [...products];

  share() {
    window.alert('The product has been shared!');
  }

  onNotify() {
    window.alert('You will be notified when the product goes on sale');
  }
}
````
