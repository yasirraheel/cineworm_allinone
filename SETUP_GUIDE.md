# Setup Guide - All In One Video

## Quick Setup Steps

### 1. Database Configuration

Edit `includes/connection.php` and update your database credentials:

```php
// For localhost
DEFINE ('DB_USER', 'root');           // Your MySQL username
DEFINE ('DB_PASSWORD', '');           // Your MySQL password  
DEFINE ('DB_HOST', 'localhost');      // Usually localhost
DEFINE ('DB_NAME', 'your_db_name');   // Your database name
```

### 2. Import Database

1. Create a new database in phpMyAdmin
2. Import the SQL file: `install/database.sql`
3. Or run the installation wizard at: `http://localhost/php_web_services_allinone/install/`

### 3. Bypass Verification (Development Mode)

The app is configured with bypass mode for easy testing:

**Access Admin Panel:**
- URL: `http://localhost/php_web_services_allinone/`
- Default login: Check database `tbl_admin` table

**Verify Purchase (Optional):**
- URL: `http://localhost/php_web_services_allinone/verification.php`
- Username: `buyer`
- Purchase Code: `xyz` (or anything)
- Package Name: `com.yourapp.name`

This will generate `api.php` file.

### 4. API Endpoint

After verification, API will be available at:
```
http://localhost/php_web_services_allinone/api.php
```

### 5. Troubleshooting

**No view showing?**
- Check if `includes/.lic` file exists (created automatically)
- Verify database connection in `includes/connection.php`
- Check PHP errors by enabling: `error_reporting(E_ALL);` in connection.php
- Make sure you've imported the database

**Admin login?**
- Default credentials are in the database
- Check `tbl_admin` table after importing database.sql

### 6. File Permissions

Ensure these folders are writable:
- `uploads/`
- `images/`
- `filemanager/uploads/`

---

## Need Help?

1. Check database connection
2. Import database.sql
3. Run installation at `/install/`
4. Or manually configure connection.php
