Yii2 Sendgrid Extension
=======================
Sendgrid Mailer for Yii 2

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist rahulk-k/yii2-sendgrid "*"
```

or add

```
"rahulk-k/yii2-sendgrid": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by :

To use Mailer, you should configure it in the application configuration like the following,
```php
'components' => [
	...
	'sendgrid' => [
		'class' => 'rahul\sendgrid\Mailer',
		'username' => 'your_user_name',
		'password' => 'your password here',
                'token'    => 'your token',
		//'viewPath' => '@app/views/mail', // your view path here
	],
	...
],
```
To send an email, you may use the following code:

```php
Yii::$app->sendgrid->compose('contact/html', ['contactForm' => $form])
->setFrom(['from@domain.com'=>'John Due'])
	->setTo($form->email)
	->setSubject($form->subject)
	->send();
```
