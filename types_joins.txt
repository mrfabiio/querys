-- 1) O primeiro JOIN é entre a tabela 'vendas' e a tabela 'produtos'.
--    Estou usando INNER JOIN e trazendo apenas os valores correspondentes em ambas as tabelas.
SELECT *
   FROM 
    vendas v
    INNER JOIN produtos p 
        ON v.produto_id = p.produto_id

-- 2) O segundo JOIN é um LEFT JOIN entre a tabela 'vendas' (à esquerda) e a tabela 'clientes' (à direita).
--    Pega todos os valores da tabela 'vendas' e os valores correspondentes da tabela 'clientes'.
--    Se não houver correspondência na tabela 'clientes', os valores dos campos da tabela 'clientes' serão nulos.
    LEFT JOIN clientes c 
        ON v.id_cliente = c.id_cliente

-- 3) O terceiro JOIN é um RIGHT JOIN entre a tabela 'produtos' (à esquerda) e a tabela 'marcas' (à direita).
--    Pega todos os valores da tabela 'marcas' e os valores correspondentes da tabela 'produtos'.
--    Se não houver correspondência na tabela 'produtos', os valores dos campos da tabela 'produtos' serão nulos.
    RIGHT JOIN marcas m
        ON p.marca_id = m.marca_id;

-- EXPLICAÇÃO ADICIONAL:
-- - O INNER JOIN entre 'vendas' e 'produtos' garante que apenas os registros com correspondências em ambas as tabelas sejam retornados.
-- - O LEFT JOIN entre 'vendas' e 'clientes' retorna todos os registros da tabela 'vendas' e, quando não há correspondência, os valores dos campos de 'clientes' são NULL.
-- - O RIGHT JOIN entre 'produtos' e 'marcas' retorna todos os registros da tabela 'marcas' e, quando não há correspondência, os valores dos campos de 'produtos' são NULL.

-- O código a seguir é um exemplo separado de um FULL JOIN:
SELECT *
    FROM 
        vendas v
    FULL JOIN clientes c
        ON v.id_cliente = c.id_cliente;
-- FULL JOIN e FULL OUTER JOIN são equivalentes.
-- Retorna todas as linhas da tabela 'vendas' (à esquerda) e todas as linhas da tabela 'clientes' (à direita).
-- Preenche com NULL onde não há correspondência.

