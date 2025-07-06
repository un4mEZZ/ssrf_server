# SSRF Server
1) To run server:
```cmd
.venv\Scripts\activate
pip install -r requirements.txt
python server.py
python target_server.py
```

2) Run Burp Suite or similar software
3) Open http://127.0.0.1:8000 or http://localhost:8000 in Burp Browser
4) Enter any valid URL (e.g. https://soundcloud.com/keinemusik)
5) Find latest POST request from 127.0.0.1:8000 and add this request to Repeater (ctrl + R)
6) Change https://soundcloud.com/keinemusik to http://127.0.0.1:8000
7) Select 8000 with LMB and send it to Inrtuder (ctrl + I)
8) Select Payload type -> Numbers -> Number range from 8990 to 9010 (to find it faster) -> Start attack
9) Find port 9000 with status 200 OK. 
10) Return to Repeater and replace URL with http://127.0.0.1:9000
11) Find secret info at http://127.0.0.1:9000/secret
