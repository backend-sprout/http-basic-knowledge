# URI와 웹 브라우저 요청 흐름  
# URI  
URI : Uniform Resource Identifier (리소스를 식별하는 통합된 방법)   

`URI?`, `URL?`, `URN?`   
  
**URI**      
URI는 로케이터(L)와 이름(N) 또는 둘다 추가로 분류될 수 있다.      
즉, 더 URL 과 URN 을 둘다 포함하는 더 큰 개념의 명사로 이해해도 된다.   
   
* Uniform : 리소스를 식별하는 통일된 방식   
* Resource : 자원, URI로 식별할 수있는 모든 것(제한 없음)
* Identifier : 다른 항목과 구분하는데 필요한 정보   

**URL(Uniform Resource Locator)**   
`foo://example.com:8042/over/there?name=ferret#nose`
     
* Locator : 리소스가 있는 위치를 지정 
* 위치는 변할 수 있다.  
* 현재 대부분의 URI 는 URL 방식을 사용하고 디렉토리와 동일시하여 리소스를 찾는다.    
       
**URN(Uniform Resource Name)**   
`urn:example:animal:ferrat:nose`  

* Name : 리소스에 이름을 부여한다.   
* 이름은 변할 수 없다.   
* `urn:isbn:8960777331`   
* 그러나 위와 같이 이름만으로는 실제 리소스를 찾을 수 있는 방법이 보편화되어 있지 않다.   
 

**URL 분석**   
URL의 기본 포멧팅은 아래와 같다.    
`schema://[userinfo@]host[:port][/path][?query][#fragment]`
   
예시를 URL은 아래와 같다.     
`https://www.google.com/search?q=hello&hl=ko`     

* `schema` : `https`
    * 주로 프로토콜을 사용한다.  
    * 프로토콜 : 어ㄸ너 자원에 접근할 것인가 하는 약속 규칙  
        * http, https, ftp 등등 
    * http는 80 포트, https는 443 포트를 주로 사용, 포트는 생략 가능하다.   
    * https는 http에 보안을 추가한 것이다.(HTTP Secure)   
* `[userinfo@]` : 생략됨  
    * URL에 사용자 정보를 포함해서 인증한다.   
    * 거의 사용하지 않는다.     
* `host` : `www.google.com`  
    * 호스트명
    * 도메인명 또는 IP 주소를 직접 사용 가능하다.   
* `[:port]` : 생략되었다.  
    * 포트(PORT)
    * 접속 포트
    * 원래는 생략하면 완 되지만, schema를 통해 유추가 가능하다.   
    * 즉, 앞자리에 `http`, `https`, `ftp`가 들어오면 생략 가능하다.   
* `[/path]` : `/search`  
    * 리소스 경로를 나타내며 주로, 계층적 구조로 되어있다.   
    * 즉, 실제 디렉터리와 동일하면 계층 구조를 그대로 가져간다. 
        * `/home/file1.jpg`
        * `/members`
        * `/members/100`
        * `/items/iphone12`
* `[?query]` : `q=hello&hl=ko`  
    * `key=value` 형태로 시작한다.   
    * `?`로 시작하며, `&`로 추가한다.   
    * query parameter, query string 등으로 불린다.   
    * 웹서버에 제공하는 파라미터, 문자 형태이다.   
*     


# 웹 브라우저 요청 흐름  
