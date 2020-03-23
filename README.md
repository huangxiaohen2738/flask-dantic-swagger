### flask-dantic-swagger

Use the pydantic to validate your request or response in flask,
and it can help you generate swagger quickly.

------------------
``` test/app.py
    @app.route("/")
    @validate(query=Book, body=Author)
    def test_route():
        book_title = request.query_params.title
        author = request.body_params
        author_books = author.books
        return jsonify(author)
    
    test_api = Blueprint("test-api", __name__)

<<< from flask_dantic_swagger import generate_swagger
<<< generate_swagger(app, "")
<<< generate_swagger(app, "test-api") 
```
