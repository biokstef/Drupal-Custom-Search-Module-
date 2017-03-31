Drupal Custom Search Module
---------------------------

It is a module that you can use for a view that has exposed filters.

You have to open .module file and change these parameters in the function below


function search_products_form_submit($form, &$form_state) {

    $title_prod = &$form_state['values']['produit'];
    //$form_state['redirect'] = 'search-products?title=' . trim($title_prod). $url ;
    $form_state['redirect'] = array(
        'search-products', // the link of the view
		//parameters of the link
        array('query' => array(
            'title' => trim($title_prod),
            'field_categorie_produit_tid' => 'All',
            'commerce_price_amount%5Bmin%5D' => '500',
            'commerce_price_amount%5Bmax%5D' => '50000'
        )));
}






