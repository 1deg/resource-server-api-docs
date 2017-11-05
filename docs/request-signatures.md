# Requests

## Request Signature

### Why we use a request signature

A request signature is a common cryptographic technique that enables the receiver of a message to confirm the identity of the sender.

### How it works

Just add a timestamp and request signature as two additional HTTP headers to all `POST`, `PUT`, and `DELETE` requests.

1. The timestamp header is labeled `1deg-Date` and is an ISO 8601-formatted timestamp at UTC, **without milliseconds or time zone**. For example, "2017-11-05T20:54:51Z" Note: Depending on the language you're using, the ISO 8601 format may be slightly different. Make sure you are using the "YYYY-MM-DDTHH:mm:ssZ" format and getting the time in UTC (Zulu).

2. The request signature header is labeled `1deg-Signature`. See below for instructions on how to construct it.

### Construct the request signature

This should be a hexadecimal digest of lowercase letters and numbers. It should be constructed as follows:

1. Create an HMAC SHA256 hexadecimal digest of the body of the request, using your API secret token as the key.

2. Create a digest of the ISO 8601-formatted timestamp submitted in the `1deg-Date` header, using the string created in step 1 above as the key.

3. Create a digest of the string created in step 2.

### Example Code

#### Ruby

	require 'time'
	require 'openssl'

	time 			= Time.now.utc
	signed_body 	= OpenSSL::HMAC.hexdigest('sha256', secret, body)
	signed_date 	= OpenSSL::HMAC.hexdigest('sha256', signed_body, time.iso8601)
	signature 	   	= Digest::SHA2.hexdigest(signed_date)

### JavaScript

	const crypto 			= require('crypto');
	
	const today				= new Date();
	const time_formatted 	= today.toISOString().split('.')[0]+'Z'; // Date().toISOString() actually returns milliseconds so needs massaging

	const signed_body 		= crypto.createHmac('sha256', secret).update(body).digest('hex');
	const signed_date 		= crypto.createHmac('sha256', signed_body).update(time_formatted).digest('hex');
	const signature 		= crypto.createHash('sha256').update(signed_date).digest('hex');
