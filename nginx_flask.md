## Serving Flask with NGINX

Go back and check out [Lab 25. 💻 NGINX Server Blocks](https://live.alta3.com/content/tlg-devops/labs/content/devops/nginx-server-blocks.html). In that lab we:
- created and started two flask servers on ports `9001` and `9002`.
- created a `.conf` file that directed nginx to listen to port `2224` and direct traffic appropriately. Here's what that may have looked like:

```nginx
server {
    listen 2224;
    server_name _;
    
    location / {
    root /var/www/html;
    index index.html; 
    }
    
    location /flask1 {
        proxy_pass http://127.0.0.1:9001; 
    }

    location /flask2 {
        proxy_pass http://127.0.0.1:9002; 
    }

}
```

### OBJECTIVE:
- revisit a previous flask project of yours. **MAKE A COPY OF IT, DON'T EDIT THE EXISTING PROJECT**.
- Change the last line of that flask code to run on a DIFFERENT PORT THAN 2224 OR 2225.
- Write a new `.conf` file in `/etc/nginx/conf.d/` to write a server block directing incoming traffic to listen on port `2225` and direct traffic to location `/` to your flask server.
- You're strongly encouraged to use the steps in lab 25 to help!  
