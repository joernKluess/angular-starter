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

```ts


````
