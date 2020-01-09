<template>
  <div>
    <pre style="text-align: left">
      {{
`
# For a quick start check out our HTTP Requests collection (Tools|HTTP Client|Open HTTP Requests Collection) or
# paste cURL into the file and request will be converted to HTTP Request format.
#
# Following HTTP Request Live Templates are available:
# * 'gtrp' and 'gtr' create a GET request with or without query parameters;
# * 'ptr' and 'ptrp' create a POST request with a simple or parameter-like body;
# * 'mptr' and 'fptr' create a POST request to submit a form with a text or file field (multipart/form-data);
GET http://123.56.246.220:30000/api/all
Accept: application/json

###
#删除

POST http://123.56.246.220:30000/api/delete
Content-Type: application/json

{
	"album_id": "3766916",
	"album_name": "Pay the Man (Remix)",
	"public_time": "2017-12-13",
	"week": 50,
	"price": 78,
	"cover": "http://imgcache.qq.com/music/photo/album_300/16/300_albumpic_3766916_0.jpg",
	"singers": [{
		"singer_id": "28132",
		"singer_name": "Foster The People"
    }],
    "_id": "5e16844774cd841c3c8c308c"
  }

###

POST http://123.56.246.220:30000/api/add
Content-Type: application/json

{
	"album_id": "3766916",
	"album_name": "Pay the Man (Remix)",
	"public_time": "2017-12-13",
	"week": 50,
	"price": 78,
	"cover": "http://imgcache.qq.com/music/photo/album_300/16/300_albumpic_3766916_0.jpg",
	"singers": [{
		"singer_id": "28132",
		"singer_name": "Foster The People"
    }]
  }
###
        `
      }}
    </pre>
  </div>
</template>
