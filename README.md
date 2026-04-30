# O11y — Prometheus + Grafana + Node Exporter

Stack de observabilidade local com Prometheus, Node Exporter e Grafana via Docker Compose.

## Componentes

| Serviço         | Porta  | Descrição                                            |
| --------------- | ------ | ---------------------------------------------------- |
| Prometheus      | `9090` | Coleta e armazena métricas                           |
| Node Exporter   | `9100` | Expõe métricas do host (CPU, memória, disco, rede)   |
| Grafana         | `3000` | Visualização de dashboards (login padrão admin/admin)|

## Pré-requisitos

- Docker
- Docker Compose

## Como subir

```bash
docker compose up -d
```

## Acessos

- Prometheus: http://localhost:9090
- Node Exporter: http://localhost:9100/metrics
- Grafana: http://localhost:3000

## Configurar Grafana

1. Acesse http://localhost:3000 e faça login (`admin` / `admin`).
2. Adicione um data source do tipo **Prometheus** com a URL `http://prometheus:9090`.
3. Importe um dashboard do Node Exporter (ex.: ID `1860` no [Grafana Dashboards](https://grafana.com/grafana/dashboards/)).

## Como derrubar

```bash
docker compose down
```

## Estrutura

```
.
├── docker-compose.yml   # Define os serviços
├── prometheus.yml       # Configuração de scrape do Prometheus
└── README.md
```
