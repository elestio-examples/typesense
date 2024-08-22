# Typesense CI/CD pipeline

<a href="https://dash.elest.io/deploy?source=cicd&social=dockerCompose&url=https://github.com/elestio-examples/coolify"><img src="deploy-on-elestio.png" alt="Deploy on Elest.io" width="180px" /></a>

Deploy Typesense server with CI/CD on Elestio

<img src="typesense.png" style='width: 30%;'/>
<br/>
<br/>

# Once deployed ...

You can open Typesense API here:

    URL: https://[CI_CD_DOMAIN]/health
    TYPESENSE_API_KEY: [TYPESENSE_API_KEY]

## API Access

### Health

Get health information about a Typesense node.

    curl "https://[CI_CD_DOMAIN]/health"

### Cluster Metrics
Get current RAM, CPU, Disk & Network usage metrics.

    curl "https://[CI_CD_DOMAIN]/metrics.json" \
        -H "X-TYPESENSE-API-KEY: ${TYPESENSE_API_KEY}"

### Clear cache

Responses of search requests that are sent with use_cache parameter are cached in a LRU cache. To clear this cache completely:

    curl -X POST "https://[CI_CD_DOMAIN]/operations/cache/clear" \
      -H "X-TYPESENSE-API-KEY: ${TYPESENSE_API_KEY}"

### API Stats
Get stats about API endpoints.

This endpoint returns average requests per second and latencies for all requests in the last 10 seconds.

    curl "https://[CI_CD_DOMAIN]/stats.json" \
      -H "X-TYPESENSE-API-KEY: ${TYPESENSE_API_KEY}"


### API Documentation

- [API Resource](https://typesense.org/docs/26.0/api/api-keys.html)
- [Analytics & Query Suggestions](https://typesense.org/docs/26.0/api/analytics-query-suggestions.html)
- [Conversational Search (RAG)](https://typesense.org/docs/26.0/api/conversational-search-rag.html)
- [Vector Search](https://typesense.org/docs/26.0/api/vector-search.html#use-cases)
- For more information, refer to the Typesense [Official Documentation](https://typesense.org/docs/26.0/api/)