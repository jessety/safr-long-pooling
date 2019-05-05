# safr-long-polling

An example shell script that uses long polling with the SAFR platform.

## Usage

This script expects two parameters: the contents of the `X-RPC-AUTHORIZATION` header, and the contents of the `AUTHORIZATION` header. Both values are required to authenticate an API call.

```bash
$ sh event_long_polling.sh x-rpx-authorization-value authorization-value
```

As per [the API specification](https://cv-event.int2.real.com/docs/index.html#/Long_Polling_Interfaces/pollStatusUsingGET), the `X-RPC-AUTHORIZATION` header contains the user/account id and the base64 encoded version of the password, joined by a colon. The `AUTHORIZATION` header should contain the directory account ID.

For example, if your username was `test` and password was `password`, the script would be invoked like this:

```bash
$ sh event_long_polling.sh test:cGFzc3dvcmQ= main
```
