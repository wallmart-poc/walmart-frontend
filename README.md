# walmart-frontend · Frontend

Browser-facing Go web application. Serves the storefront HTML, manages user sessions, handles currency selection, and routes all user actions to the appropriate downstream gRPC services.

## Stack
- **Language:** Go 1.21
- **Framework:** `net/http` + Go templates
- **Session:** Cookie-based

## Running locally
```bash
go mod vendor
go run .
```
Service listens on port `8080` by default (`FRONTEND_PORT`). Set `LISTEN_ADDR` to override the bind address.

## Dependencies
All downstream services are configured via environment variables:

| Env var | Service |
|---|---|
| `PRODUCT_CATALOG_SERVICE_ADDR` | walmart-product-catalog |
| `CURRENCY_SERVICE_ADDR` | walmart-currency |
| `CART_SERVICE_ADDR` | walmart-cart |
| `RECOMMENDATION_SERVICE_ADDR` | walmart-recommendations |
| `CHECKOUT_SERVICE_ADDR` | walmart-checkout |
| `SHIPPING_SERVICE_ADDR` | walmart-shipping |
| `AD_SERVICE_ADDR` | walmart-ads |
| `SHOPPING_ASSISTANT_SERVICE_ADDR` | walmart-shopping-assistant |

