# Python 3 script: generate_business_website.py
# This script generates a basic HTML website for a sample business.

business_name = "Green Bean Coffee Co."
tagline = "Savor the Taste of Sustainability"
description = """
Green Bean Coffee Co. is an eco-friendly coffee shop committed to sourcing organic,
fair-trade coffee and minimizing our environmental footprint. Join us for a cup
that’s good for you and the planet.
"""
my-website/
  index.html   
  README.md

products = [
    {"name": "Organic Espresso", "price": "$3.50", "description": "Rich, bold, and sustainably sourced."},
    {"name": "Vegan Latte", "price": "$4.50", "description": "Creamy oat milk with premium espresso."},
    {"name": "Eco Blend Coffee Beans", "price": "$12.99", "description": "Take home our signature beans in compostable packaging."},
]
contact_info = {
    "address": "123 Green Street, Eco City, Earth",
    "phone": "(123) 456-7890",
    "email": "info@greenbeancoffee.com"
}
image_urls = [
    "https://via.placeholder.com/300x200?text=Coffee+Shop",
    "https://via.placeholder.com/300x200?text=Espresso",
    "https://via.placeholder.com/300x200?text=Latte"
]

html_content = f"""
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{business_name}</title>
    <style>
        body {{ font-family: Arial, sans-serif; margin: 0; padding: 0; background-color: #f4f4f4; }}
        header {{ background-color: #2c3e50; color: white; padding: 20px 0; text-align: center; }}
        h1 {{ margin: 0; }}
        section {{ padding: 20px; }}
        .products {{ display: flex; flex-wrap: wrap; gap: 20px; }}
        .product {{ background: white; padding: 15px; border-radius: 10px; width: 300px; }}
        img {{ max-width: 100%; border-radius: 10px; }}
        footer {{ background: #2c3e50; color: white; padding: 10px; text-align: center; }}
    </style>
</head>
<body>
    <header>
        <h1>{business_name}</h1>
        <p>{tagline}</p>
    </header>

    <section>
        <h2>About Us</h2>
        <p>{description}</p>
    </section>

    <section>
        <h2>Our Products</h2>
        <div class="products">
"""

for i, product in enumerate(products):
    html_content += f"""
            <div class="product">
                <img src="{image_urls[i]}" alt="{product['name']}">
                <h3>{product['name']}</h3>
                <p>{product['description']}</p>
                <strong>{product['price']}</strong>
            </div>
    """

html_content += f"""
        </div>
    </section>

    <section>
        <h2>Contact Us</h2>
        <p>Address: {contact_info['address']}</p>
        <p>Phone: {contact_info['phone']}</p>
        <p>Email: {contact_info['email']}</p>
    </section>

    <footer>
        <p>&copy; 2025 {business_name}. All rights reserved.</p>
    </footer>
</body>
</html>
"""

# Save HTML file
with open("index.html", "w") as file:
    file.write(html_content)

print("Website generated successfully! Open 'index.html' in your browser to view it.")
