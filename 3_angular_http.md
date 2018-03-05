
### Integrate Angular Http Request

#### Task 1: Create static json file [ 20 mins]
* assets/data/courses.json
```
[ { "coursename": "Java" }, {"coursename":"MySQL"} ]
```

#### Task 2: Enable Http in "app.module.ts"
```
import { HttpClientModule } from '@angular/common/http';

imports: [
    HttpClientModule,    
  ..]
```

#### Task 3: Add Http call
* home.ts
```
import { HttpClient } from '@angular/common/http';

constructor(private http: HttpClient) {
    
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

#### Task 4: Display Courses in html
* home.html
```
Course List:
{{courses|json}}
```



