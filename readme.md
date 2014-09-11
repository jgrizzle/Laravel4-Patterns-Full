## Laravel - Patterns demo application - Full version

This is the full version for the Laravel4-Patterns template given below.
It includes all the files required to run the demo.

https://github.com/octabrain/Laravel4-Patterns/

For more information checkout the above repository.

### How to use it

#### Step 1

From the console run

	$composer update
	$composer dump-autoload -o

#### Step 2

Create a database with following structure :

	CREATE TABLE IF NOT EXISTS users (
		`id` int(11) NOT NULL AUTO_INCREMENT,
		`username` varchar(255) NOT NULL,
		`updated_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
		`created_at` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
		PRIMARY KEY (`id`)
	) ENGINE=InnoDB  DEFAULT CHARSET=utf8 AUTO_INCREMENT=1;

Add the database configuration to the app/config/database.php

Add some dummy data also.

#### Test

Make a POST request to the URL http://<your-laravel-url>/public/api/user/create

	$curl -X POST http://<your-laravel-url>/public/api/user/create

This request should fail with hex validation error.

Remove the 'hex' rule from app/lib/Sampleapp/Services/Validators/UserValidator.php

	$curl -X POST http://<your-laravel-url>/public/api/user/create

This request should succeed.

Make a GET request to the URL http://public/api/user/index

	$curl -X GET http://<your-laravel-url>/public/api/user/index

This request should succeed.

### License

The MIT License (MIT)

Copyright (c) 2014 https://github.com/octabrain

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
