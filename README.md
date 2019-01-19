About HelmJ Tiller Client
--------------------------------

Helm has two parts, one of them is client and the other is server which is called Tiller.
Tiller communicates with the Kubernetes API to manage your charts.  
   
While it is doing that, it uses gRPC. gRPC is an open source remote procedure call (RPC) system initially developed at Google.
gRPC uses protocol buffers. 

Helm Team defined some proto files to run it and we will use those well-defined proto files to create java client to communicate Tiller.
Those files are also used by go client.

How to build a client ?
-----------------

If you want to create a client, just run > **mvn package**

Be Aware of versioning
---------------------------------

1.0.0-e70bea6  <- it is an example for readme.

- 1.0.0 is our version
- e70bea6 last commit of proto folder for https://github.com/helm/helm/tree/master/_proto 

Where are the real proto files ?
---------------------------------

You can visit that link => https://github.com/helm/helm/tree/master/_proto

Protobuf3 type declarations for the Helm API
--------------------------------------------

Packages

 - `hapi.chart` Complete serialization of Heml charts
 - `hapi.release` Information about installed charts (Releases) such as metadata about when they were installed, their status, and how they were configured.
 - `hapi.services.rudder` Definition for the ReleaseModuleService used by Tiller to manipulate releases on a given node
 - `hapi.services.tiller` Definition of the ReleaseService provided by Tiller and used by Helm clients to manipulate releases cluster wide.
 - `hapi.version` Version meta-data used by tiller to express it's version
 
 Last part copied from => https://github.com/helm/helm/blob/master/_proto/README.md