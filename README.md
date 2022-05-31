# Read Easy Backend 
### Runner up in BuildwithAi international Hackathon


Create a virtualenv
```
virtualenv [ your env name ]
```
Create .env file in backend folder with the following fields. Replace the value according to your environment.

```env
DATABASE=postgres
DB_USER=db_user_name
DB_PASSWORD=db_password
HOST_ADDRESS=localhost:5432
DB_NAME=db_name
```
Install Packages
```
pip install -r requirements.txt
```
Create DB (Postgres)
```
createdb db_name
```
**Development Server**
```bash
export FLASK_APP=server
export FLASK_ENV=development

# run migrations once
flask db upgrade

flask run
```

## API Documentation

* Auth Login /login method ="POST"
```yaml
{
  email
  password
}
```
Response

```yaml
 {
                "success": True,
                "name": body["username"],
                "email": body["email"],
                "role": body["role"],
                "id": user.id,
  }
```

* Get all Student Courses

```javascript
@student.route("/getallcourse", methods=["GET"])
def getallcourse():
    result = Course.query.all()
    courses = [course.format_short() for course in result]
    
    return jsonify({"message": "success","courses": courses})
```

* OCR

```javascript
@student.route("/ocr", methods=["POST"])
def ocr():
    f = request.get_json()
    im = f["image"].split("base64,")[1]
    ----------------------------------
    return jsonify({"message": "success","prediction": class_names[np.argmax(score)]})
```

            

