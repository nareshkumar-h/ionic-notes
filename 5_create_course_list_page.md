#### Create Course List Page

#### Task 1: Create CourseListPage
```
ionic g page CourseList --no-module
```

#### Task 2: Declare the page
```
import { CourseListPage } from '../pages/course-list/course-list';

 declarations: [
    CourseListPage
  ]
 entryComponents: [
    CourseListPage    
  ],
```

#### Task 3: Add a Button for Navigation to the page
* home.html
```
<button ion-button color="secondary" (click)="showCourses()"> Show Courses</button>
```
* home.ts
```
 showCourses(){
    console.log("Go to CourseList Page");
    this.navCtrl.push(CourseListPage);
  }
```

#### Task 4: Move course logic from HomePage to CourseList Page
* course-list.ts
```
courses:Object;

constructor(public navCtrl: NavController, public navParams: NavParams, private http: HttpClient) {
  }
  
ngOnInit() {
    this.loadCourses();
  }

  loadCourses(){
    this.http.get('assets/data/courses.json').subscribe( data => {
      this.courses = data;
    });
  }
  
```

#### Task 5: List courses 
* course-list.html
```
 <ion-list>
        <button ion-item *ngFor="let c of courses" (click)="openCourse(c)">
          {{c.coursename}}
        </button>
      </ion-list>
```
  
