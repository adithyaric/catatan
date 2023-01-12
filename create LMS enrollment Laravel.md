To create a learning management system (LMS) with enrollment functionality in Laravel, you will need to perform the following steps:

1.  Install Laravel and set up a new project.
2.  Set up a database and configure your Laravel project to connect to it.
3.  Create a model and migration for your courses. A course will represent a class or subject that students can enroll in.
4.  Create a model and migration for your users. Users will represent students and instructors who can enroll in and teach courses.
5.  Set up authentication for your Laravel project. This will allow users to log in and access the LMS.
6.  Create a controller and corresponding views for enrolling in courses. This will allow users to view a list of available courses and enroll in them.
7.  Add a enrollment status field to the users table. This will allow you to track which courses a user is enrolled in.
8.  Implement functionality to view a list of enrolled courses and unenroll from courses.
9.  (Optional) Add additional features to your LMS, such as the ability to create and manage courses, assign instructors to courses, and post announcements and assignments.

I hope this helps! Let me know if you have any questions.

Here is an example of what the code for the enrollment functionality in your Laravel app might look like:

In the `Course` model:
```php
<?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class Course extends Model
{
    public function users()
    {
        return $this->belongsToMany('App\User')->withPivot('enrollment_status');
    }
}
```

In the `User` model:

```php
<?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class User extends Model
{
    public function courses()
    {
        return $this->belongsToMany('App\Course')->withPivot('enrollment_status');
    }
}
```

In the `CoursesController`:

```php
<?php

namespace App\Http\Controllers;

use App\Course;
use Illuminate\Http\Request;

class CoursesController extends Controller
{
    public function index()
    {
        // Retrieve a list of all courses
        $courses = Course::all();

        return view('courses.index', compact('courses'));
    }

    public function enroll(Course $course)
    {
        // Enroll the authenticated user in the specified course
        $user = auth()->user();
        $user->courses()->attach($course, ['enrollment_status' => 'enrolled']);

        return redirect()->route('courses.index')->with('success', 'You have successfully enrolled in the course.');
    }

    public function unenroll(Course $course)
    {
        // Unenroll the authenticated user from the specified course
        $user = auth()->user();
        $user->courses()->detach($course);

        return redirect()->route('courses.index')->with('success', 'You have successfully unenrolled from the course.');
    }
}
```

In the `courses.index` view:

```php
@foreach($courses as $course)
    <h3>{{ $course->name }}</h3>
    @if(auth()->check())
        @if(auth()->user()->isEnrolledIn($course))
            <form method="POST" action="{{ route('courses.unenroll', $course) }}">
                @csrf
                <button type="submit" class="btn btn-danger">Unenroll</button>
            </form>
        @else
            <form method="POST" action="{{ route('courses.enroll', $course) }}">
                @csrf
                <button type="submit" class="btn btn-primary">Enroll</button>
            </form>
        @endif
    @endif
@endforeach
```


Here is an example of what the database schema and columns for a learning management system (LMS) with enrollment functionality might look like:

**Courses table:**

-   id: The primary key for the courses table.
-   name: The name of the course.
-   description: A brief description of the course.
-   created_at: The date and time when the course was created.
-   updated_at: The date and time when the course was last updated.

**Users table:**

-   id: The primary key for the users table.
-   name: The name of the user.
-   email: The email address of the user.
-   password: The hashed password for the user.
-   created_at: The date and time when the user was created.
-   updated_at: The date and time when the user was last updated.

**Course_user pivot table:**

-   course_id: The id of the course that the user is enrolled in. This is a foreign key to the courses table.
-   user_id: The id of the user who is enrolled in the course. This is a foreign key to the users table.
-   enrollment_status: The enrollment status of the user in the course. This can be "enrolled", "completed", or any other status that you define.

This is just an example and you may need to customize the schema and columns to fit the needs of your specific LMS.

---
## add middleware

Yes, you can restrict users who have not enrolled in a course from accessing the course content in your LMS. To do this, you can use Laravel's built-in authentication and authorization features.

For example, you can define a `viewCourse` middleware that checks if the authenticated user is enrolled in the specified course before allowing them to view the course content. Here is an example of what that middleware might look like:

```php
<?php

namespace App\Http\Middleware;

use Closure;

class viewCourse
{
    public function handle($request, Closure $next)
    {
        $course = $request->route('course');
        if (auth()->check() && auth()->user()->isEnrolledIn($course)) {
            return $next($request);
        }
        return redirect()->route('courses.index')->with('error', 'You are not enrolled in this course.');
    }
}
```

You can then apply this middleware to the routes that display course content, like this:

```php
Route::get('courses/{course}', 'CoursesController@show')->middleware('viewCourse');
```

This will ensure that only users who are enrolled in the course will be able to view the course content. If a user who is not enrolled in the course tries to access the content, they will be redirected to the course index page with an error message.

---
## add a payment system

To add a payment system to your learning management system (LMS) so that users can pay for courses before enrolling in them, you will need to perform the following steps:

1.  Set up a payment gateway to process payments. There are many options available, such as Stripe, PayPal, and Braintree. You will need to create an account with the payment gateway and obtain any necessary API keys or credentials.
    
2.  Install a package or integration to interface with the payment gateway in your Laravel app. For example, if you are using Stripe, you can install the `laravel/cashier` package.
    
3.  Add a `paid` field to the `course_user` pivot table to track whether a user has paid for a course.
    
4.  Modify the enrollment process to require payment before allowing a user to enroll in a course. You can do this by displaying a payment form to the user and using the payment gateway's API to process the payment. If the payment is successful, you can mark the user as paid and allow them to enroll in the course.
    

Here is an example of what the code for the modified enrollment process might look like:

```php
public function enroll(Course $course)
{
    if (auth()->check()) {
        $user = auth()->user();
        if ($user->hasPaidFor($course)) {
            // Enroll the user in the course
            $user->courses()->attach($course, ['enrollment_status' => 'enrolled']);

            return redirect()->route('courses.index')->with('success', 'You have successfully enrolled in the course.');
        } else {
            // Display the payment form
            return view('courses.pay', compact('course'));
        }
    }
    return redirect()->route('login');
}

public function pay(Course $course, Request $request)
{
    if (auth()->check()) {
        $user = auth()->user();
        // Use the payment gateway's API to process the payment
        $result = $paymentGateway->charge($request->input('stripeToken'), $course->price);
        if ($result->success) {
            // Mark the user as paid and enroll them in the course
            $user->courses()->attach($course, ['enrollment_status' => 'enrolled', 'paid' => true]);

            return redirect()->route('courses.index')->with('success', 'You have successfully enrolled in the course.');
        } else {
            return redirect()->back()->with('error', 'There was an error processing your payment: ' . $result->message);
        }
    }
    return redirect()->route('login');
}
```

Here is an example of what the model and database schema for a learning management system (LMS) with a payment system for enrolling in courses might look like:

**Courses model:**

```php
<?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class Course extends Model
{
    public function users()
    {
        return $this->belongsToMany('App\User')->withPivot('enrollment_status', 'paid');
    }
}
```

**Users model:**

```php
<?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class User extends Model
{
    public function courses()
    {
        return $this->belongsToMany('App\Course')->withPivot('enrollment_status', 'paid');
    }

    public function hasPaidFor(Course $course)
    {
        return $this->courses()->where('course_id', $course->id)->wherePivot('paid', true)->exists();
    }
}
```

**Courses table:**

-   id: The primary key for the courses table.
-   name: The name of the course.
-   description: A brief description of the course.
-   price: The price of the course.
-   created_at: The date and time when the course was created.
-   updated_at: The date and time when the course was last updated.

**Users table:**

-   id: The primary key for the users table.
-   name: The name of the user.
-   email: The email address of the user.
-   password: The hashed password for the user.
-   created_at: The date and time when the user was created.
-   updated_at: The date and time when the user was last updated.

**Course_user pivot table:**

-   course_id: The id of the course that the user is enrolled in. This is a foreign key to the courses table.
-   user_id: The id of the user who is enrolled in the course. This is a foreign key to the users table.
-   enrollment_status: The enrollment status of the user in the course. This can be "enrolled", "completed", or any other status that you define.
-   paid: A boolean value indicating whether the user has paid for the course.

This is just an example and you may need to customize the model and schema to fit the needs of your specific LMS.