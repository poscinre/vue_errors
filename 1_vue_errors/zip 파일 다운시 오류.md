# zip 파일 다운시 오류

```javascript
{
  headers: {
    responseType: "blob",
  }, 
}
```

<br>
* 기존에는 위와 같이 작성 했는데, 아래와 같이 수정 후 zip 파일이 다운 가능해짐.
<br>
<br>

```javascript
API 이름 : async (
    sp: SearchParam
  ): Promise<
    [
      number,
      string,
      (
        | AxiosResponseHeaders
        | Partial<
            Record<string, string> & { "set-cookie"?: string[] | undefined }
          >
      )
    ]
  > => {
    try {
      const { data, status, headers } = await RestClient.post<string>(
        `경로`,
        sp,
        {
          responseType: "blob",
          headers: {
            Accept: "application/zip",
          }, 
        }
      );
      return [status, data, headers];
    } catch (e: unknown) {
      const errorCode = 500;
      const errorMessage = "An error occurred";
      const errorHeaders = {};
      return [errorCode, errorMessage, errorHeaders];
    }
  },
```
