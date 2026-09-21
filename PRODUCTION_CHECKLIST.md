# Production activation checklist

1. Provision PostgreSQL/Supabase and migrate schema.
2. Set JWT_SECRET and OTP provider secrets in server environment.
3. Configure Paytm server-side and payment callback/webhook verification.
4. Configure push notifications (FCM/APNs) and maps/GPS provider.
5. Configure HTTPS + API domain + CORS allowlist.
6. Create owner/admin account and remove bootstrap route/key.
7. Turn Marketplace ON only after seller/FSSAI/KYC workflow is approved.
8. Verify HALAL label is shown on products, orders and QR verification.
9. Add backups, audit logs, rate limits, monitoring and error alerts.
10. Build signed Android/iOS releases and submit to stores.
