# VVIP MARKET PALACE — Production Activation

This package is production-oriented code, but external services must be configured with real credentials before accepting live customers.

## Required secrets/services
- PostgreSQL (recommended for production persistence)
- JWT_SECRET: long random secret
- OTP_PROVIDER_API_KEY: real SMS/OTP provider key
- PAYTM_SECRET_KEY: real Paytm production secret, stored only as a server environment variable
- CORS_ORIGINS: production customer/admin/delivery origins

## Security
- Keep OTP_DEV_MODE=false in production.
- Never commit Paytm secret, JWT secret, OTP key, or database password.
- Do not use the bootstrap endpoint in an internet-exposed production deployment; create the first admin through a protected provisioning process and then disable/remove bootstrap.
- QR payload contains an order token, not customer phone/address.

## Live flow
Customer -> OTP -> Cart -> Order -> Admin -> Delivery assignment -> QR verification -> Delivered.

The existing SQLite implementation is suitable for local/demo use. For production multi-city/PAN-India scale, migrate persistence to PostgreSQL before launch.
