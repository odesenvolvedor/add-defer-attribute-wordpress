# add-defer-attribute-wordpress
Script para adicionar atributo defer na tag script para WordPress.

Após um dia inteiro tentando resolver um problema no WordPress, 
quando eu ativava o checkout do Mercado Pago, 
ocorria vários erros de JavaScript. 
Quando descobri que o erro ocorria no momento de carregar o script exterdo no SDK do Mercado Pago, eu encontrei a solução no artigo do Matthew Horne
em seu blog: https://matthewhorne.me/defer-async-wordpress-scripts/

O exemplo serve para qualquer script que precisa ser adiado o carregamento, bastando adicionar o nome no array $scripts_to_defer.

Exemplo de uso:
```php
function add_defer_attribute($tag, $handle) {
    // add script handles to the array below
    $scripts_to_defer = array('mercado-pago-module-custom-js');
    
    foreach($scripts_to_defer as $defer_script) {
       if ($defer_script === $handle) {
          return str_replace(' src', ' defer="defer" src', $tag);
       }
    }
    return $tag;
 }
 add_filter('script_loader_tag', 'add_defer_attribute', 10, 2);
```
