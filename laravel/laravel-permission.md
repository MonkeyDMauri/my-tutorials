# Laravel permissions for storage and bootstrap/cache (Apache or Nginx)

This guide explains how to setup the correct permissions for a new laravel app so the server and you have the necessary permissions to run it.

---

## ✅ Prerequisites


---

When setting up a laravel app, there are 2 directories your web server needs the right access to, the first one
is the **your-laravel-app/storage/** directory and the secodn one is a directory whitin your bootstrap directory called cache 
so the location would be **your-laravel-app/bootstrap/cache/**.

---

## 1. Identify under what user your server is running as.

```bash
ps aux | egrep '(apache|httpd|nginx)'

This command will show us the name of the user the server is running as, from the output
identify the user from the left column which tells us the system user the server is using (usually www-data),
ignore any processes owned by **root**.

## 2. Change ownership

Knowing the system user the server is running as we'll update **storage** and **bootstrap/cache** to be owned by www-data with the following command.

```bash
sudo chown -R www-data storage
sudo chown -R www-data bootstrap/cache

---

We should now be able to load our laravel application with out any permission errors.

