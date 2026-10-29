# Wheekly
* Simple weekly sprint / goal tracker
* Uses localStorage, or can connect to sqlite database local or webDAV (nginx only)

## Requires
* apache2-utils (htpasswd)
* nginx
* certbot for SSL

## WEBDAV
* use basic auth for protection (requires apache2-utils for htpasswd) - weak but for utility use, fine
* create and save to /db/ folder (e.g. https://wheekly.example.com/dbs/week-47.sqlite
* MULTI USER to same DB WILL overwrite; use dedicated DB / watch for multiuser.

### suggested fix:
- Remember the version: keep the ETag from the GET that loaded the project.
- Check on return and every ~30 s: when the tab regains focus or becomes visible, plus on that timer, send a HEAD request. If the ETag changed and you have no unsaved edits, reload the project quietly.
- Check before every save: send a HEAD first. If the server copy changed since you loaded it, don't PUT. Show "Changed elsewhere — reload" so you can reload instead of overwriting.

