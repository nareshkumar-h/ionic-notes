## Display Courses

#### Task 1: Iterate and Display courses
```
  <ion-list>
    <button ion-item *ngFor="let c of courses" (click)="openCourse(c)">
      {{c.name}}
    </button>
  </ion-list>
  ```
  
 #### Task 2: Enable Click
 * home.ts
 ```
 openCourse(course){
    console.log(course);
  }
  ```
  
  #### Task 3: Navigate to another page
  ```
    constructor(public navCtrl: NavController, private http: HttpClient) {
    }


  openCourse(course){
    console.log(course);
    this.navCtrl.push(AboutPage,  {'course':course } );
  }
  ```
