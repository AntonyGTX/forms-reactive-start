This is a html part

<div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-10 col-md-8 col-sm-offset-1 col-md-offset-2">
        <form [formGroup]="exampleForm" (ngSubmit)="submitedForm()">
          <div formGroupName="userData">
            <div class="form-group">
              <label for="username">Username</label>
              <input
                type="text"
                id="username"
                class="form-control"
                formControlName="userName"
                >
                <span
                 *ngIf="!exampleForm.get('userData.userName').valid && exampleForm.get('userData.userName').touched"
                 class="alert-danger" >
                   <span *ngIf="exampleForm.get('userData.userName').errors['required']">This field is required!</span>
                   <span *ngIf="exampleForm.get('userData.userName').errors['user is forbidden']">This name is Not allowed</span>
                </span>
                
            </div>
            <div class="form-group">
              <label for="email">email</label>
              <input
                type="text"
                id="email"
                class="form-control"
                formControlName="email"
                >
               <span
               class="alert-danger"
               *ngIf="!exampleForm.get('userData.email').valid && exampleForm.get('userData.email').touched"
               >
                Provide a valid email address
               </span>
            </div>
          </div>                                                                              
          <div class="radio" *ngFor="let gender of genders">
            <label>
              <input
                type="radio"
                formControlName="gender"
                [value]="gender">{{ gender }}
            </label>
          </div>
          <div formArrayName="Hobies">
            <h4>Add a Hobie you like</h4>
            <button 
              class="button"
              type="button"
              (click)=" onsetValue()"
              >Add Hobie</button>
            <div class="form-group" *ngFor="let hobbyControl of HobiesAdd">
              <ul class="list-group">
                <li class="list-item" value="hobies">{{hobbyControl}}</li>
              </ul>
            </div>
          </div>
          <button class="button" type="submit">Submit</button>
        </form>
      </div>
    </div>
  </div>
  
