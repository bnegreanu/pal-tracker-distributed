pal-tracker-distributed codebase

```
cd ~/workspace/assignment-submission
./gradlew cloudNativeDeveloperDistributedSystemWithSecurity \
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

Token: 7e895995-d078-43d5-9996-250e153a2468

curl localhost:8083 -H"Authorization: Bearer 7e895995-d078-43d5-9996-250e153a2468"

allocations-pal-djb.apps.evans.pal.pivotal.io
backlog-pal-djb.apps.evans.pal.pivotal.io
registration-pal-djb.apps.evans.pal.pivotal.io
timesheets-pal-djb.apps.evans.pal.pivotal.io


curl -k "https://p-identity.login.sys.evans.pal.pivotal.io/oauth/token" -i -u "723ce2ad-fc3a-4dc7-b7bc-d89c1d77cca7:336de5c9-dfad-4286-bb89-7bc177f0403e" -X POST -H 'Accept: application/json' -H 'Content-Type: application/x-www-form-urlencoded' -d 'grant_type=client_credentials&response_type=token'

./gradlew cloudNativeDeveloperDistributedSystemWithSecurity \
    -PuaaUrl=https://p-identity.login.sys.evans.pal.pivotal.io \
    -PclientId=723ce2ad-fc3a-4dc7-b7bc-d89c1d77cca7 \
    -PclientSecret=336de5c9-dfad-4286-bb89-7bc177f0403e \
    -PregistrationServerUrl=https://registration-pal-djb.apps.evans.pal.pivotal.io \
    -PbacklogServerUrl=https://backlog-pal-djb.apps.evans.pal.pivotal.io \
    -PallocationsServerUrl=https://allocations-pal-djb.apps.evans.pal.pivotal.io \
    -PtimesheetsServerUrl=https://timesheets-pal-djb.apps.evans.pal.pivotal.io



cf create-service p-config-server standard tracker-config-server \
-c "{\"git\": {\"uri\": \"https://github.com/dhwajad/tracker-config.git\", \"label\": \"master\"}}"

./gradlew cloudNativeDeveloperDistributedSystemWithConfigServer \
    -PuaaUrl=https://p-identity.login.sys.evans.pal.pivotal.io \
    -PclientId=723ce2ad-fc3a-4dc7-b7bc-d89c1d77cca7 \
    -PclientSecret=336de5c9-dfad-4286-bb89-7bc177f0403e \
    -PregistrationServerUrl=https://registration-pal-djb.apps.evans.pal.pivotal.io \
    -PbacklogServerUrl=https://backlog-pal-djb.apps.evans.pal.pivotal.io \
    -PallocationsServerUrl=https://allocations-pal-djb.apps.evans.pal.pivotal.io \
    -PtimesheetsServerUrl=https://timesheets-pal-djb.apps.evans.pal.pivotal.io