# Genio V1 Production

## Architecture
Microsoft Entra ID -> Azure Static Web Apps -> Azure Functions API -> Azure SQL.

## Migration sequence
1. Create Azure SQL database and execute database/schema.sql.
2. Add SQL_CONNECTION_STRING to the Function/Static Web App application settings.
3. Deploy /api and validate GET /api/health.
4. Seed the JDE Benelux project, project blocks, actions, decisions and milestones from the current source.
5. Switch the frontend read path from localStorage to API with a temporary fallback.
6. Enable central create/update/delete and audit logging.
7. Add Excel import preview with New / Changed / Unchanged / Conflict before apply.
8. Add Microsoft Graph reminder service after central data is stable.

## Safety rule
Do not remove localStorage fallback until the Azure API and SQL database are validated in production.
