# LEP

## Graphql Daemon
- Environment Setup
    ```
    1. ./buildImage.sh
    2. docker-compose up
    ```
- Start
    1. curl -g 'http://localhost:8889/graphql?query={memory{total,free,buffers,cached,time}}'
    ```
    {"data":{"memory"[
    {"total":1000.0,"free":865.0,"buffers":78.0,"cached":69.0,"time":"2017-09-30T04:06:49.274760223Z"},{"total":1000.0,"free":875.0,"buffers":78.0,"cached":96.0,"time":"2017-09-30T04:07:00.420316864Z"},{"total":1000.0,"free":775.0,"buffers":48.0,"cached":92.0,"time":"2017-09-30T04:07:23.612781013Z"},{"total":1000.0,"free":715.0,"buffers":44.0,"cached":72.0,"time":"2017-09-30T04:07:36.824906679Z"}]
    }}
    ```
    2. curl -g 'http://localhost:8889/graphql?query={memory{host,total,free,time}}'
    ```
    {"data":{"memory":
    [{"host":"127.0.0.0","total":1000.0,"free":865.0,"time":"2017-09-30T04:06:49.274760223Z"},{"host":"127.0.0.0","total":1000.0,"free":875.0,"time":"2017-09-30T04:07:00.420316864Z"},{"host":"127.0.0.0","total":1000.0,"free":775.0,"time":"2017-09-30T04:07:23.612781013Z"},{"host":"127.0.0.0","total":1000.0,"free":715.0,"time":"2017-09-30T04:07:36.824906679Z"}
    ]}
    ```
    3. curl -g 'http://localhost:8889/graphql?query={memoryFilter(host:"127.0.0.1",start:"2017-09-20T13:21:54Z",end:"2017-09-30T13:55:05Z"){total,free,buffers,cached,time}}'
    ```
    {"data":{"memoryFilter":[{"total":1000.0,"free":865.0,"buffers":78.0,"cached":69.0,"time":"2017-09-30T13:54:04.625575757Z"},{"total":1000.0,"free":865.0,"buffers":72.0,"cached":78.0,"time":"2017-09-30T13:54:18.190049902Z"},{"total":1000.0,"free":490.0,"buffers":77.0,"cached":90.0,"time":"2017-09-30T13:54:31.984802329Z"},{"total":1000.0,"free":40.0,"buffers":77.0,"cached":90.0,"time":"2017-09-30T13:54:36.288140308Z"},{"total":1000.0,"free":401.0,"buffers":37.0,"cached":89.0,"time":"2017-09-30T13:54:51.58052178Z"}]}}
    ```
    4. Open browser [http:127.0.0.1:8889/graphql](http://127.0.0.1:8889/graphql)
     ![](https://i.imgur.com/DaRbfws.png)
    