## Add Loading Bar for Server Request

#### Reference:
* https://ionicframework.com/docs/components/#loading

#### Task 1: Add Loading Bar
```
export class CourseListPage {

  courses:Object;
  

  constructor(public navCtrl: NavController, public navParams: NavParams, private http: HttpClient,public loadingCtrl: LoadingController) {
  }

  loader = this.loadingCtrl.create({content: "Please wait..."});

  ngOnInit() {    
    this.loadCourses();
  }

  loadCourses(){
    this.loader.present();
    this.http.get('assets/data/courses.json').subscribe( data => {
      this.courses = data;
      this.loader.dismiss();
    });
  }
}
```
