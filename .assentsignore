export default {
  async fetch(request, env) {
    const url = new URL(request.url);
    const path = url.pathname;

    // Link de acompanhamento do cliente: /app/pedidos/ID-DO-PEDIDO
    // -> serve o mesmo cardapio.html (ele lê o ID direto na URL)
    if (path.startsWith('/app/pedidos/')) {
      const destino = new URL('/app/cardapio.html', url);
      return env.ASSETS.fetch(new Request(destino, request));
    }

    // Link do motoboy: /app/infopedido/ID-DO-PEDIDO
    // -> serve o infopedido.html
    if (path.startsWith('/app/infopedido/')) {
      const destino = new URL('/app/infopedido.html', url);
      return env.ASSETS.fetch(new Request(destino, request));
    }

    // Qualquer outro caminho (cardapio.html, painel, imagens, etc.):
    // comportamento normal, serve o arquivo pedido sem alterar nada.
    return env.ASSETS.fetch(request);
  }
};
