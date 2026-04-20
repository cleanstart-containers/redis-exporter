# CleanStart Container for Redis Exporter

Official Redis Exporter container image optimized for enterprise environments. Includes comprehensive Prometheus metrics collection for Redis instances and monitoring capabilities. Features security-hardened base image, minimal attack surface, and FIPS-compliant cryptographic modules. Supports both production deployments and development workflows with separate tagged versions. Includes Redis exporter, metrics collection, and essential monitoring tools.

## Key Features

- Complete Redis monitoring environment with metrics collection
- Optimized for cloud-native and microservices architectures
- Support for Redis Standalone, Sentinel, and Cluster modes
- Export detailed Redis performance and operational metrics

## Common Use Cases

- Building and deploying Redis monitoring
- Cloud-native observability development
- Redis performance monitoring and alerting
- Integration with Prometheus and Grafana stacks

## Pull Commands

Download the runtime container images
```bash
docker pull ghcr.io/cleanstart-containers/redis-exporter:latest
docker pull ghcr.io/cleanstart-containers/redis-exporter:latest-dev
```

## Interactive Development

Start interactive session for development
```bash
docker run --rm -it --entrypoint /bin/sh ghcr.io/cleanstart-containers/redis-exporter:latest-dev
```

## Container Start

Start the container
```bash
docker run --rm -it --name redis-exporter-dev -p 9121:9121 -e REDIS_ADDR=redis://localhost:6379 ghcr.io/cleanstart-containers/redis-exporter:latest
```

## Configuration Options

The Redis Exporter supports various configuration options via environment variables:

- `REDIS_ADDR`: Redis server address (default: redis://localhost:6379)
- `REDIS_PASSWORD`: Redis password for authentication
- `REDIS_USER`: Redis user for ACL authentication
- `REDIS_EXPORTER_CHECK_KEYS`: Comma-separated list of keys to export
- `REDIS_EXPORTER_CHECK_SINGLE_KEYS`: Comma-separated list of single keys to export
- `REDIS_EXPORTER_SKIP_TLS_VERIFICATION`: Skip TLS certificate verification

## Example with Authentication
```bash
docker run --rm -p 9121:9121 \
  -e REDIS_ADDR=redis://redis:6379 \
  -e REDIS_PASSWORD=yourpassword \
  ghcr.io/cleanstart-containers/redis-exporter:latest
```

## Best Practices

- Use specific image tags for production (avoid latest)
- Configure resource limits: memory and CPU constraints
- Enable read-only root filesystem when possible
- Use authentication for Redis instances
- Set up proper network security and firewall rules

## Architecture Support

### Multi-Platform Images
```bash
docker pull --platform linux/amd64 ghcr.io/cleanstart-containers/redis-exporter:latest
docker pull --platform linux/arm64 ghcr.io/cleanstart-containers/redis-exporter:latest
```

---

## Documentation Resources
Essential links and resources for further information
 
**CleanStart Images**: https://images.cleanstart.com/
 
**Community Images**:
**Docker Hub**: https://hub.docker.com/u/cleanstart<br>
**GitHub**: https://github.com/cleanstart-containers<br>
**AWS ECR Public Gallery**: https://gallery.ecr.aws/cleanstart/
 
**Presence on Social Media**:
**Community**: https://www.linkedin.com/groups/18324021/<br>
**YouTube**: https://www.youtube.com/@CleanStartOfficial<br>
 
**Contribute to Container Use Cases**: https://github.com/cleanstart-dev/cleanstart-use-cases/
