# add-defer-attribute-wordpress
Script para adicionar atributo defer na tag script para WordPress.

Após um dia inteiro tentando resolver um problema no WordPress, 
quando eu ativava o checkout do Mercado Pago, 
ocorria vários erros de JavaScript. 
Quando descobri que o erro ocorria no momento de carregar o script exterdo no SDK do Mercado Pago, eu encontrei a solução no artigo do Matthew Horne
em seu blog: https://matthewhorne.me/defer-async-wordpress-scripts/

O exemplo serve para qualquer script que precisa ser adiado o carregamento.
