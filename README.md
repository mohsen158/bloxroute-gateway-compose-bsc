# bloXroute Gateway Docker Compose for BSC

This repository contains a Docker Compose configuration for running the bloXroute Gateway on the BSC (Binance Smart Chain) network.

## Prerequisites

- Docker and Docker Compose installed
- Access to a BSC node
- bloXroute account and credentials
- SSL certificates (if required)

## Quick Start

1. **Clone and navigate to the repository:**
   ```bash
   cd bloxroute-gateway-compose-bsc
   ```

2. **Copy the environment template:**
   ```bash
   cp env.example .env
   ```

3. **Edit the `.env` file with your configuration:**
   ```bash
   nano .env
   ```

4. **Create required directories:**
   ```bash
   mkdir -p logs ssl
   ```

5. **Start the gateway:**
   ```bash
   docker-compose up -d
   ```

## Configuration

### Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `LOG_FILE_PATH` | Path to log files directory | `./logs` |
| `SSL_CERT_PATH` | Path to SSL certificates | `./ssl` |
| `BLOCKCHAIN_NETWORK` | Blockchain network name | `BSC-Mainnet` |
| `BLOCKCHAIN_NODE_PUBLIC_KEY` | Your BSC node's public key | `abc123...` |
| `NODE_IP` | Your BSC node's IP address | `192.168.1.100` |
| `NODE_PORT` | Your BSC node's port | `30303` |
| `ENR` | Ethereum Node Record string | `enr:-...` |
| `PRIVATE_KEY` | Your private key (keep secure!) | `0x...` |
| `ETH_WS_URI` | WebSocket URI to your ETH node | `ws://192.168.1.100:8546` |

### Ports

- **1801**: WebSocket port for API access
- **28333**: P2P port for node communication

## Usage

### Start the service
```bash
docker-compose up -d
```

### View logs
```bash
docker-compose logs -f bxgateway-go
```

### Stop the service
```bash
docker-compose down
```

### Restart the service
```bash
docker-compose restart
```

## Security Notes

- Never commit your `.env` file to version control
- Keep your private key secure and never share it
- Use proper SSL certificates in production
- Consider using Docker secrets for sensitive data

## Troubleshooting

1. **Check container status:**
   ```bash
   docker-compose ps
   ```

2. **View detailed logs:**
   ```bash
   docker-compose logs bxgateway-go
   ```

3. **Verify network connectivity:**
   ```bash
   docker-compose exec bxgateway-go ping your_node_ip
   ```

## Support

For issues related to bloXroute Gateway, refer to the official bloXroute documentation and support channels.
