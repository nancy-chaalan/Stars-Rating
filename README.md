Angular Stars Rating Project
This Angular project provides a simple and intuitive star rating system for products. The star rating is easily customizable, and the code is kept clean and minimal.

Features:

Easy Integration: Quickly integrate the star rating component into your Angular project.
Customizable Styling: The star icons change color to orange when hovered or selected.
Dynamic Rating Display: The number of stars rated is displayed dynamically.
Straightforward Code: The TypeScript function starsRating handles the rating logic with simplicity.
Usage
Copy the HTML and CSS components from this project.
Add the star rating component to your Angular module.
Customize the styling and adjust the number of stars as needed.



HTML Component
html
Copy code

<div class="ratingDiv">
    <p class="title">Rate The Product :</p>
    
    <div class="stars">
        <a (click)="starsRating(1)" [ngClass]="{'notChecked1': true, 'isChecked1': isChecked1}" class="fa fa-star"></a>
        <a (click)="starsRating(2)" [ngClass]="{'notChecked2': true, 'isChecked2': isChecked2}" class="fa fa-star"></a>
        <a (click)="starsRating(3)" [ngClass]="{'notChecked3': true, 'isChecked3': isChecked3}" class="fa fa-star"></a>
        <a (click)="starsRating(4)" [ngClass]="{'notChecked4': true, 'isChecked4': isChecked4}" class="fa fa-star"></a>
        <a (click)="starsRating(5)" [ngClass]="{'notChecked5': true, 'isChecked5': isChecked5}" class="fa fa-star"></a>
        <p class="reviews">({{starsRated}}) Stars</p>
    </div>
</div>






CSS Styling
css
Copy code

/* ======================== Whole Div ======================== */
.ratingDiv {
    padding: 50px;
}

/* ======================== TEXTS ======================== */
.title {
    font-weight: 600;
    color: blueviolet;
    font-size: 20px;
}

.stars .reviews {
    padding: 0;
    margin: 0 10px;
}  

/* ======================== STARS ======================== */

.stars {
    display: flex;
}

.stars a {
    text-decoration: none;
    margin: 5px 1px;
    cursor: pointer;
    color: grey;
}

.stars .notChecked1:hover,
.stars .notChecked3:hover,
.stars .notChecked2:hover,
.stars .notChecked4:hover,
.stars .notChecked5:hover {
    color: orange; 
}

/* this css here will be achieved when isChecked is == true  */
.stars .isChecked1,
.stars .isChecked2,
.stars .isChecked3,
.stars .isChecked4,
.stars .isChecked5 {
    color: orange;
}





TypeScript Logic
typescript
Copy code
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'stars';

  // Default value is false, so stars will take the default CSS which is grey
  isChecked1 = false;
  isChecked2 = false;
  isChecked3 = false;
  isChecked4 = false;
  isChecked5 = false;

  // For the rating value
  starsRated = 0;

  constructor() {}

  starsRating(rating: number) {
    // Change value to true, so stars will take the isChecked CSS which is orange
    // Rating value is the number of stars selected 

    if (rating === 1) {
      this.isChecked1 = true;
      this.starsRated = 1;
      this.isChecked2 = this.isChecked3 = this.isChecked4 = this.isChecked5 = false;
    } else if (rating === 2) {
      this.isChecked1 = this.isChecked2 = true;
      this.starsRated = 2;
      this.isChecked3 = this.isChecked4 = this.isChecked5 = false;
    } else if (rating === 3) {
      this.isChecked1 = this.isChecked2 = this.isChecked3 = true;
      this.starsRated = 3;
      this.isChecked4 = this.isChecked5 = false;
    } else if (rating === 4) {
      this.isChecked1 = this.isChecked2 = this.isChecked3 = this.isChecked4 = true;
      this.starsRated = 4;
      this.isChecked5 = false;
    } else if (rating === 5) {
      this.isChecked1 = this.isChecked2 = this.isChecked3 = this.isChecked4 = this.isChecked5 = true;
      this.starsRated = 5;
    } else {
      this.isChecked1 = this.isChecked2 = this.isChecked3 = this.isChecked4 = this.isChecked5 = false;
    }
  }
}






USER VIEW :

![Screenshot 2023-12-22 124125](https://github.com/nancy-chaalan/Stars-Rating/assets/150782100/59b66d17-7ea7-4628-82fa-6d65bb7483cf)
![Screenshot 2023-12-22 124115](https://github.com/nancy-chaalan/Stars-Rating/assets/150782100/ff32d995-5e19-45a9-928b-58dabace8340)
![Screenshot 2023-12-22 124107](https://github.com/nancy-chaalan/Stars-Rating/assets/150782100/1ba9fd44-3a4c-4580-b215-44f02d023cf9)






CODE :

![Screenshot 2023-12-22 125238](https://github.com/nancy-chaalan/Stars-Rating/assets/150782100/4212f1ce-93b7-4002-8a1f-287c1c607110)
![Screenshot 2023-12-22 124148](https://github.com/nancy-chaalan/Stars-Rating/assets/150782100/5faa1497-cd0b-470c-8990-37949ecd96a5)
![Screenshot 2023-12-22 125315](https://github.com/nancy-chaalan/Stars-Rating/assets/150782100/0442072e-3b02-4f4a-b976-5d145c6fc6dd)



