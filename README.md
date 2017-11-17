1. Run Image
docker run --name my_solr -d -p 8983:8983 -t solr
2. Show container
docker-ps
3. Delete
docker kill my_solr
docker rm my_solr

An Example:
docker run --name solr_demo -d -P solr solr-demo

Core Creation into container
docker exec -it solr_demo solr create_core -c dummy_core

Copy data into container
docker cp generated.json solr_demo:/opt/solr/generated.json

Load Dummy Data
docker exec -it solr_demo post -c dummy_core generated.json

Core creation new container:
docker run -d -P solr solr-create -c dummy_core

show more:
https://github.com/docker-solr/docker-solr
