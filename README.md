#### Change header on scrool
.sticky-header {
   top: -70px !important;
   z-index: -1;
   transition: top 1s ease !important;
}
.sticky-header.elementor-sticky--effects {
    top: 0 !important;
    z-index:10;
}


### Stop order from guest user
## >> Go to woocommerce > setting > Account & privaciy > Enable log-in during checkout(Enable this one)
## if user not register the website but if you want that user redirect to the login page use this php code 
#### add_action('template_redirect', 'redirect_to_custom_login_page');
function redirect_to_custom_login_page() {
    if (is_checkout() && !is_user_logged_in()) {
        // Redirect to your custom login page
        wp_redirect('https://brandingstore.infinityfreeapp.com/login/?redirect_to=' . wc_get_page_permalink('checkout'));
        exit;
    }
}

