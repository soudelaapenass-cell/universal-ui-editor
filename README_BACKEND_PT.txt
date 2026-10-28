LZN SEARCH — BACKEND (PORTUGUÊS)

O que faz
- Entrega resultados em JSON para a interface própria do LZN Browser.
- Consulta uma instância SearXNG configurada por você.
- Tem categorias Web, Imagens, Vídeos, Notícias, Ciência e Arquivos.
- Região define a preferência de idioma/região enviada ao SearXNG.
- Safe search é mantido em estrito ou padrão. Não há modo exclusivo para conteúdo adulto.
- O filtro de conteúdo por IA é heurístico (títulos/descrições), não é um classificador perfeito.
- Filtro de cor acrescenta a cor à consulta; não garante que todos os resultados tenham essa cor.

IMPORTANTE
Este código não cria sozinho um índice completo de todos os sites. Para ter resultados, hospede o backend e conecte-o a uma instância SearXNG (metabuscador). Um índice realmente próprio exigiria crawler, políticas de robots.txt, armazenamento, deduplicação, ranking e servidores permanentes.

Executar localmente (Python 3.10+):
  pip install -r requirements.txt
  export SEARXNG_URL=http://127.0.0.1:8080
  uvicorn main:app --host 0.0.0.0 --port 8000

Em Windows PowerShell, definir variável:
  $env:SEARXNG_URL="http://127.0.0.1:8080"
  uvicorn main:app --host 0.0.0.0 --port 8000

Configure a instância SearXNG com saída JSON habilitada. Publique o backend por HTTPS antes de acessá-lo pela internet. Não exponha servidor de desenvolvimento diretamente à internet; use HTTPS/reverse proxy e limites de requisição.

No LZN Browser: escolha motor LZN, faça uma busca, toque em “Configurar servidor LZN” e informe a URL HTTPS do backend (por exemplo, https://search-api.seudominio.com).
