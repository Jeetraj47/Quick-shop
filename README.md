from flask import Flask, render_template, request

app = Flask(__name__)

# Sample data for demonstration
grocery_items = [
    {"name": "Apples", "price": 120},
    {"name": "Bananas", "price": 40},
    {"name": "Milk", "price": 30},
    {"name": "Bread", "price": 25},
]

@app.route('/')
def index():
    return render_template('index.html', items=grocery_items)

@app.route('/add_to_cart', methods=['POST'])
def add_to_cart():
    item_name = request.form['name']
    # Add item to the cart (implementation not shown)
    return f"{item_name} added to cart!"

if __name__ == '__main__':
    app.run(debug=True)
