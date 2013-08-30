# Requests

## Request Signature

### Why we use a request signature

A request signature is a common cryptographic technique that enables the receiver of a message to confirm the identity of the sender.

### How it works

Just add a timestamp and request signature as two additional HTTP headers to all `POST`, `PUT`, and `DELETE` requests.

1. The timestamp header is labeled `1deg-Date` and is an ISO 8601-formatted timestamp.
2. The request signature header is labeled `1deg-Signature`. See below for instructions on how to construct it.

### How to construct the request signature

This should be a hexadecimal digest of lowercase letters and numbers. It should be constructed as follows:

1. Create the string to sign:
    
    1. Take the parameters being submitted with the request, and sort the parameters alphabetically in descending order. These parameters should include any resource ID parameters specified in the endpoint. For example, the parameters collection for the endpoint `/v1/resources/:resource_id/locations/:id` should include `resource_id` and `id`.
    1. URL encode the parameter names and values. Use `%20` for space (' ') instead of `+`.
    2. Connect each parameter in a `key=value` format and append them to each other, joined by ampersands (`&`). For example, `name=Organization%20Inc&description=An%20example`.

2. Create an HMAC digest of the string created in step 1, using your API secret token as the key.

3. Create an HMAC digest of the ISO 8601-formatted timestamp submitted in the `1deg-Date` header, using the string created in step 2 as the key.

4. Create a SHA2 hexadecimal digest of the string created in step 3.

### Example Code

#### Ruby

    require 'time'
    require 'openssl'
    require 'erb'

    params = {
        resource_id: 3841,
        name: "Existing Resource Provider, Inc."
        website: "http://www.this.isan/example" 
    }
    param_string = ""
    params.keys.sort.each do |key|
        param_string << "&" unless str.blank?
        param_string << "#{ERB::Util.url_encode(key.to_s)}=#{ERB::Util.url_encode(params[key].to_s)}"
    end
    date = Time.now.utc.iso8601
    signed_params = OpenSSL::HMAC.digest('sha256', my_secret_token, param_string)
    signed_date = OpenSSL::HMAC.digest('sha256', signed_params, date)
    signature = Digest::SHA2.hexdigest(signed_date)

### Python

    # TODO this is where a Python code example will go.
