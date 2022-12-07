# How-to-customize-Laravel-pagination-links
Como personalizar os links de paginação do Laravel
How to customize Laravel pagination links

#1. Adicionar paginação
Para facilitar a navegação na lista de usuários, você só pode exibir dez por vez. O Laravel permite que você use o método paginate() para agrupar os resultados da consulta.

Para usar paginate, em vez de get, você precisa atualizar a consulta no arquivo web.php, conforme mostrado abaixo.
EXEMPLO::: ＄users = User::paginate(10);

Adicione os links de paginação à exibição:
{{ ＄users->links() }}

#2 . Publish pagination views
Para personalizar os links, você precisa acessá-los e editá-los. Por padrão, os links estão na pasta do fornecedor, mas podem ser publicados para seu uso.

Para ver uma lista de todos os ativos publicáveis, execute o seguinte comando.
EXEMPLO :: php artisan vendor:publish

#3. Edite e use
Agora, em seu método de inicialização AppServiceProvider, diga ao Paginator para usar o Bootstrap, conforme mostrado abaixo.
public function boot()
{
    Paginator::useBootstrap();
}
