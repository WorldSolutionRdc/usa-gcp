# Proxy Nginx pour VPS New York (199.19.72.98)

Proxy Nginx déployé sur Google Cloud Run pour rediriger le trafic TCP vers le VPS principal.

## Configuration
| Élément | Valeur |
|---------|--------|
| **VPS cible** | `199.19.72.98:443` |
| **Port d'écoute proxy** | `8080` |
| **Région VPS** | `us-east4` (New York, USA) |
| **Région Cloud Run** | `europe-west2` (Londres, Royaume-Uni) |
| **Type de proxy** | TCP Stream (Layer 4) |

## Déploiement
```bash
gcloud run deploy newyork-proxy \
  --source . \
  --platform managed \
  --region europe-west2 \
  --allow-unauthenticated \
  --port 8080 \
  --memory 512Mi \
  --cpu 1 \
  --timeout 3600
