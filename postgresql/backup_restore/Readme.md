## Automated Backup
1. Use pg_backup.config to configure backup configs.
2. Use pg_backup.sh to run backup. (need permission `chmod +x`)
3. Use pg_backup_rotated.sh to run daily, weekly, monthly backup. (need permission `chmod +x`)
4. Create .pgpass at home directory (like /home/larry or root) to store postgresql password.
5. After create .pgpass, then for security reasons, we must disallow access to the file to world or group. `chmod 0600 ~/.pgpass`
6. Schedule run the backup command by cron job `cron_pattern ./pg_backup.sh -c pg_backup.config`
```
00 23 * * * ./pg_backup.sh -c pg_backup.config
@daily ./pg_backup.sh -c pg_backup.config
```
