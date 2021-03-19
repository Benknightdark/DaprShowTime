# dapr show time
```Bash
# simple usage
dapr run --app-id myapp --dapr-http-port 3500 --components-path ./my-components
curl http://localhost:3500/v1.0/secrets/my-secret-store/my-secret

# distributed invoke
dapr run --app-id multiplyapp --app-port 5000 --dapr-http-port 3502 -- python3.9 -m flask run
dapr stop --app-id multiplyapp
http://localhost:3502/v1.0/invoke/multiplyapp/method/multiply
curl -w "\n" -s 'http://localhost:3502/v1.0/invoke/multiplyapp/method/multiply' -H 'Content-Type: application/json' --data '{"operandOne":"52","operandTwo":"34"}'

dapr run --app-id webapp --app-port 3000 --dapr-http-port 3503  npm run dev
dapr stop --app-id webapp
```
# Reference
- integrate docker compose 
    - https://docs.microsoft.com/zh-tw/dotnet/architecture/dapr-for-net-developers/getting-started
    