# Magento External Checkout for Vue Storefront

This Magento extension allow You to merge given shopping cart with current's user session. It performs a auto-login if user-token provided.

This module is designed to work with: [Vue Storefront External Checkout](https://github.com/Vendic/vsf-external-checkout).

This extension allows the user to start the session within the Vue Storefront shop and finalize the order in Magento2. It's great when You have very extended/customized Magento checkout which will  be hard to port to Vue Storefront.

![External checkout for Vue Storefront](https://raw.githubusercontent.com/Vendic/vsf-external-checkout/master/media/diagram.png)

### Demo
[A demo is not yet available.](https://github.com/Vendic/magento2-external-checkout/issues/1)

### Compatibility
- Magento 2.2 or Magento 2.3

### Prerequisites (the Vue Storefront part)
1. Integrate Your Magento2 instance with Vue Storefront: [tutorial](https://medium.com/@piotrkarwatka/vue-storefront-cart-totals-orders-integration-with-magento2-6fbe6860fcd), [video tutorial](https://www.youtube.com/watch?v=CtDXddsyxvM)
2. Install  [Vue Storefront External Checkout](https://github.com/Vendic/vsf-external-checkout) on your Vue Storefront instance

### Installation guide (the Magento 2 part)
1. Install the module with composer:
```bash
composer require vuestorefront/magento2-vue-cart-sync
```
3. Run `php bin/magento setup:upgrade`
4. Please install the [`vsf-external-checkout`](https://github.com/Vendic/vsf-external-checkout) module for Vue Storefront. [See the instruction](https://github.com/Vendic/vsf-external-checkout).
5. Go to: Stores -> Configuration | VueStorefront -> External Checkout and set URL

To test if Your extension works just fine, You can test the following URL:
* http://your-base-magento-address.io/vue/cart/sync/token/{customer-api-token}/cart/{cartId}

For example, our test address looks like:
* http://demo-magento2.vuestorefront.io/vue/cart/sync/token/s7nirf24cxro7qx1hb9uujaq4jx97nvp/cart/3648

where
* `s7nirf24cxro7qx1hb9uujaq4jx97nvp` is a customer token provided by [`POST /V1/integration/customer/token`](http://devdocs.magento.com/guides/v2.0/get-started/authentication/gs-authentication-token.html) or can be empty!
* `3648` is a quote id; for guest-carts it will be not integer but guid string

## Credits

Mateusz Bukowski (@gatzzu)
