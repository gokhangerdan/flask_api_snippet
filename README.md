# flask_api_snippet

```
from flask import Flask, request, jsonify


app = Flask(__name__)


@app.route('/controller', methods=["POST"])
def controller_function():

    response = request.get_json()
    
    return jsonify(response)


@app.after_request
def add_headers(response):
    response.headers.add('Access-Control-Allow-Origin', '*')
    response.headers.add('Access-Control-Allow-Headers', 'Content-Type,Authorization')
    return response


if __name__ == '__main__':
    app.run(host='localhost', port=5000, debug=False, threaded=True)

```
