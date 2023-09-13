# WooCommerce-Buy-Now-Button
This code allows you to dynamically create a "Buy Now" button on your WooCommerce product pages, providing a convenient one-click purchase option for your customers.

**What Does This Code Snippet Do?**

In WooCommerce, the default behavior for product pages is to have an "Add to Cart" button, which allows customers to add products to their shopping carts. However, in some cases, you may want to offer a more direct purchasing option, especially for simple products.

This code snippet enhances your WooCommerce product pages by adding a "Buy Now" button right below the "Add to Cart" button. When clicked, the "Buy Now" button immediately takes the customer to the checkout page with the selected product in the cart. This can help streamline the purchasing process, making it faster and more straightforward for your customers.

**How to Use This Code Snippet**

To implement the "WooCommerce Buy Now Button" on your website, follow these steps:

Access Your Theme's functions.php File:

Log in to your WordPress dashboard.
Go to "Appearance" > "Theme Editor."
Select your active theme.
Add the Code Snippet to functions.php:

On the right side, find and click on the functions.php file.
Scroll to the bottom of the file and paste the following code snippet:

```
/* Create Buy Now Button dynamically after Add To Cart button */
function add_content_after_addtocart() {
    // get the current post/product ID
    $current_product_id = get_the_ID();
 
    // get the product based on the ID
    $product = wc_get_product( $current_product_id );
 
    // get the "Checkout Page" URL
    $checkout_url = WC()->cart->get_checkout_url();
 
    // run only on simple products
    if( $product->is_type( 'simple' ) ){
        echo '<div class="clear-sec"></div>';
        echo '<a href="'.$checkout_url.'?add-to-cart='.$current_product_id.'" class="buy-now button">Buy Now</a>';     } }
add_action( 'woocommerce_after_add_to_cart_button', 'add_content_after_addtocart' );
```


# Save Changes

Click the "Update File" button to save your changes.
Customization
You can customize this code snippet to suit your specific needs. For example, you can modify the button's CSS class, text, or positioning on the page. You can also control the conditions under which the "Buy Now" button is displayed, such as product types or user roles.

Contributions and Issues
This open-source code snippet is hosted on GitHub to encourage collaboration and improvements from the community. If you have any ideas for enhancements or discover any issues, please feel free to open an issue on GitHub. We appreciate your involvement in making this code snippet even more useful.

License
This "WooCommerce Buy Now Button" code snippet is distributed under the GNU General Public License v2.0. It's free to use, modify, and distribute according to the terms of the license.

Thank you for considering this code snippet to enhance your WooCommerce store's user experience. We hope it helps you provide a convenient and efficient shopping process for your customers. Enjoy the benefits of a streamlined checkout!
