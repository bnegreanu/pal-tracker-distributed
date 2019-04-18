pal-tracker-distributed codebase

```
cd ~/workspace/assignment-submission
./gradlew cloudNativeDeveloperDistributedSystemWithCircuitBreaker \
    -PregistrationServerUrl=https://registration-pal-djb.apps.evans.pal.pivotal.io \
    -PbacklogServerUrl=https://backlog-pal-djb.apps.evans.pal.pivotal.io \
    -PallocationsServerUrl=https://allocations-pal-djb.apps.evans.pal.pivotal.io \
    -PtimesheetsServerUrl=https://timesheets-pal-djb.apps.evans.pal.pivotal.io
```
```

    curl -i -XPOST -H"Content-Type: application/json" https://registration-pal-djb.apps.evans.pal.pivotal.io/registration -d'{"name": "Pete"}'
    curl -i https://registration-pal-djb.apps.evans.pal.pivotal.io/users/1

    curl -i https://registration-pal-djb.apps.evans.pal.pivotal.io/accounts?ownerId=1

    curl -i -XPOST -H"Content-Type: application/json" https://registration-pal-djb.apps.evans.pal.pivotal.io/projects -d"{\"name\": \"Basket Weaving\", \"accountId\": 1}"
    curl -i https://registration-pal-djb.apps.evans.pal.pivotal.io/projects?accountId=1

    curl -i -XPOST -H"Content-Type: application/json" https://allocations-pal-djb.apps.evans.pal.pivotal.io/allocations -d"{\"projectId\": 1, \"userId\": 1, \"firstDay\": \"2015-05-17\", \"lastDay\": \"2015-05-18\"}"
    curl -i https://allocations-pal-djb.apps.evans.pal.pivotal.io/allocations?projectId=1

    curl -i -XPOST -H"Content-Type: application/json" https://backlog-pal-djb.apps.evans.pal.pivotal.io/stories -d"{\"projectId\": 1, \"name\": \"Find some reeds\"}"
    curl -i https://backlog-pal-djb.apps.evans.pal.pivotal.io/stories?projectId=1

    curl -i -XPOST -H"Content-Type: application/json" https://timesheets-pal-djb.apps.evans.pal.pivotal.io/time-entries/ -d"{\"projectId\": 1, \"userId\": 1, \"date\": \"2015-05-17\", \"hours\": 6}"
    curl -i https://timesheets-pal-djb.apps.evans.pal.pivotal.io/time-entries?userId=1
```