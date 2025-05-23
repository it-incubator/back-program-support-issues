

# Студент столкнулся с проблемой подключения к базе даных через монго дб

```

MongoServerSelectionError: 000C4DF101000000:error:0A000438:SSL routines:ssl3_read_bytes:tlsv1 alert internal error:../deps/openssl/openssl/ssl/record/rec_layer_s3.c:1590:SSL alert number 80

    at Topology.selectServer (/Users/evgeniakacarskaa/jane-project/node_modules/mongodb/lib/sdam/topology.js:303:38)
    at async Topology._connect (/Users/evgeniakacarskaa/jane-project/node_modules/mongodb/lib/sdam/topology.js:196:28)
    at async Topology.connect (/Users/evgeniakacarskaa/jane-project/node_modules/mongodb/lib/sdam/topology.js:158:13)
    at async topologyConnect (/Users/evgeniakacarskaa/jane-project/node_modules/mongodb/lib/mongo_client.js:204:17)
    at async MongoClient._connect (/Users/evgeniakacarskaa/jane-project/node_modules/mongodb/lib/mongo_client.js:217:13) {
  reason: TopologyDescription {
    type: 'ReplicaSetNoPrimary',
    servers: Map(3) {
      'ac-qbdlc6o-shard-00-02.1itx76z.mongodb.net:27017' => [ServerDescription],
      'ac-qbdlc6o-shard-00-00.1itx76z.mongodb.net:27017' => [ServerDescription],
      'ac-qbdlc6o-shard-00-01.1itx76z.mongodb.net:27017' => [ServerDescription]
    },
    stale: false,
    compatible: true,
    heartbeatFrequencyMS: 10000,
    localThresholdMS: 15,
    setName: 'atlas-8cw5rg-shard-0',
    maxElectionId: null,
    maxSetVersion: null,
    commonWireVersion: 0,
    logicalSessionTimeoutMinutes: null
  },
  code: undefined,
  [Symbol(errorLabels)]: Set(0) {},
  [cause]: MongoNetworkError: 000C4DF101000000:error:0A000438:SSL routines:ssl3_read_bytes:tlsv1 alert internal error:../deps/openssl/openssl/ssl/record/rec_layer_s3.c:1590:SSL alert number 80
  
      at connectionFailureError (/Users/evgeniakacarskaa/jane-project/node_modules/mongodb/lib/cmap/connect.js:353:20)
      at TLSSocket.<anonymous> (/Users/evgeniakacarskaa/jane-project/node_modules/mongodb/lib/cmap/connect.js:268:44)
      at Object.onceWrapper (node:events:634:26)
      at TLSSocket.emit (node:events:519:28)
      at emitErrorNT (node:internal/streams/destroy:169:8)
      at emitErrorCloseNT (node:internal/streams/destroy:128:3)
      at process.processTicksAndRejections (node:internal/process/task_queues:82:21) {
    [Symbol(errorLabels)]: Set(1) { 'ResetPool' },
    [cause]: [Error: 000C4DF101000000:error:0A000438:SSL routines:ssl3_read_bytes:tlsv1 alert internal error:../deps/openssl/openssl/ssl/record/rec_layer_s3.c:1590:SSL alert number 80
    ] {
      library: 'SSL routines',
      reason: 'tlsv1 alert internal error',
      code: 'ERR_SSL_TLSV1_ALERT_INTERNAL_ERROR'
    }
  }
} Dont connected successfully to server
```

решение - 
``` 
mongodb+srv://<username>:<password>@cluster0.mongodb.net/<нужно_было_тут_указать_название_базы>?retryWrites=true&w=majority
```


