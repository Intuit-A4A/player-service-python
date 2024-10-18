# A4A Teams model

This is a thin model wrapper container based on PlayerDB. 

To build and run:
```shell
docker build -t a4a_model .
docker run --rm -p 5000:5000  -it localhost/a4a_model:latest
```

This will expose port 5000.

To send data to the trad AI model:
```shell
$ curl -H "Content-type: application/json" -d '{"seed_id":"abbotji01","team_size":10}' http://127.0.0.1:5000/team/generate
{"seed_id":"abbotji01","team_size":10,"member_ids":["abbotji01","combspa01","maurero01","cummijo01","flemida01","macdobo01","eddych01","morriha02","mcgrifr01","blossgr01"]}
```

To send feedback:
```shell
$ curl -H "Content-type: application/json"  -d '{"seed_id":"abbotji01","member_id":"maurero01","feedback":-1}' http://127.0.0.1:5000/team/feedback 
{"seed_id":"abbotji01","member_id":"maurero01","accepted":true}
```