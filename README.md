# nginx-pathinfo
nginx配置pathinfo

```
location ~ ^(.+\.php)(.*)$ {
         fastcgi_pass   127.0.0.1:9000;
         fastcgi_index  index.php;
         fastcgi_split_path_info  ^(.+\.php)(.*)$;
         fastcgi_param PATH_INFO $fastcgi_path_info;
         if (!-e $document_root$fastcgi_script_name) {
             return 404;
         }
         fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
         include        fastcgi_params;
}
```
