# Create the product list

src/app/product-list/product-list.component.html
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

```ts


````

```ts


````

```ts


````

```ts


````

```ts


````
