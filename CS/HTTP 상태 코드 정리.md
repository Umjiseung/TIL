# HTTP 상태 코드 정리

> 상태 코드는 3자리 숫자로 만들어져 있으며, 첫번째 자리는 1에서 5까지 제공된다.

> 첫번쨰 자리가 4와 5인 경우는 정상적인 상황이 아니기 때문에 사이트 관리자가 즉시 알아야 하는 정보이다.

* 1xx(정보): 요청을 받았으며 프로세스를 계속 진행합니다.

* 2xx(성공): 요청을 성공적으로 받았으며 인식했고 수용하였다.

* 3xx(리다이렉션): 요청 완료를 위해 추가 작업 조치가 필요합니다.

* 4xx(클라이언트 오류): 요청의 문법이 잘못되었거나 요청을 처리할 수 없습니다.

* 5xx(서버 오류): 서버가 명백히 유효한 요청에 대한 충족을 실패했습니다.
---
## 1XX: Information responses

> 상태 코드가'1'로 시작하는 경우는 서버가 요청을 받았으며, 서버에 연결된 클라이언트는 작업을 계속 진행하라는 의미입니다. 해당 코드는 HTTP 1.0에서 지원되지 않습니다.

* 100 Continue

* 101 Switching Protocol

* 102 Processing(WebDAV)
---
## 2XX: Successful responses

* 200 OK

* 201 Created

* 202 Accepted

* 203 Non-Authoritative Information

* 204 No Content

* 205 Reset Content

* 206 Partial Content

* 207 Multi-Status

* 208 Already Reported

* 226 IM Used(HTTP Delta encoding)
---
## 3XX: Redirection messages

* 300 Multiple Choice

* 301 Moved Permanently

* 302 Found

* 303 See Other

* 304 Not Modified

* 305 Use Proxy

* 306 Unused

* 307 Temporary Redirect

* 308 Permanent Redirct
---
## 4XX: Client error responses

* 400 Bad Request

* 401 Unauthorized

* 402 Payment Required

* 403 Forbidden

* 404 Not Found

* 405 Method Not Allowed

* 406 Not Acceptable

* 407 Proxy Authentication Required

* 408 Request Timeout

* 409 Conflict

....

---
## 5XX: Server error responses

* 500 Internal Server Error

* 501 Not Implemented

* 502 Bad Gateway

* 503 Service Unavailable

* 504 Gateway Timeout

* 505 HTTP Version Not Supported

* 506 Variant Also Negotiates

* 507 Insufficient Storage

* 508 Loop Detected (WebDAV)

* 510 Bot Extended

* 511 Network Authentication Required
