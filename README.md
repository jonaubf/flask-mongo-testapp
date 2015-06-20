# flask-mongo-testapp
This is a simple Flask application with MongoDB on backend and simple API on frontend.

API is accessible on port 8080 and supports two methods: **GET** and **POST**

You can add a record to database sending POST request to `http://localhost:8080/api/`. Request should contain a JSON string with a next structure:

```

{"uid": "1", "name": "John Doe", "date": "2015-05-12T14:36:00.451765", "md5checksum": "e8c83e232b64ce94fdd0e4539ad0d44f"}
```

md5checksum is a MD5 checksum for the string: `{"uid": "1", "name": "John Doe", "date": "2015-05-12T14:36:00.451765"}`, you can check it on any online resource like [http://onlinemd5.com/](http://onlinemd5.com/)

You can get info about records for some UID by any single date by sending GET request to the `htpp://localhost:8080/api/<uid>/<date>/` (date format: %Y-%m-%d)

Application is deploing with vagrant and ansible

## Dependencies
- Ansible 1.9.1
- Vagrant 1.7.2
- Virtualbox 4.3

## How to deploy and run
1. At first install dependencies to your local machine. 
2. Clone this repo by doing: `git clone https://github.com/jonaubf/flask-mongo-testapp.git`
3. Go to the directory you receive: `cd flask-mongo-testapp`
4. Run deploy process: `vagrant up`
5. You can access application on `http://localhost:8080/api/`
