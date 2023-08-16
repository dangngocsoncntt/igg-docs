### Giới thiệu chung

Tài liệu hướng dẫn sử dụng SDKs.

Trong trang này sẽ bao gôm những ví dụ đơn giản nhất để tìm hiểu về chức năng của s3.

Các chức năng khi kết hợp với nhau sẽ giúp người dùng có được tính năng hay và thú vị.

<hr class="rounded">
### Cài đặt

Tạo 1 Maven project và thêm vào file pom.xml dependency sau:

``` yaml
<dependency>
    <groupId>com.amazonaws</groupId>
    <artifactId>aws-java-sdk-s3</artifactId>
    <version>1.12.522</version>
</dependency>
```
<hr class="rounded">
### Khởi tạo kết nối

Khi khởi tạo kết nối cần các thông tin <i><b>access_key</b></i>, <i><b>secret_key</b></i>, <i><b>endpoint</b></i>. 

Trong đó:

* <i><b>access_key</b></i> và <i><b>secret_key</b></i> được lấy từ <a href="https://storage-stagging.vnpt.vn">giao diện quản trị</a>.
* <i><b>endpoint</b></i> là đường dẫn tới trang quản trị

``` java linenums="1"
String accessKey = "<ACCESS_KEY>";
String secretKey = "<SECRET_KEY>";

ClientConfiguration clientConfig = new ClientConfiguration();
clientConfig.setProtocol(Protocol.HTTP);
AWSCredentials credentials = new BasicAWSCredentials(accessKey, secretKey);
AmazonS3 s3Client = AmazonS3ClientBuilder
        .standard()
        .withEndpointConfiguration(new AwsClientBuilder.EndpointConfiguration(
                endpoint,
                Regions.DEFAULT_REGION.getName()))
        .withPathStyleAccessEnabled(true)
        .withClientConfiguration(clientConfig)
        .withCredentials(new AWSStaticCredentialsProvider(credentials))
        .build();
```

### Quản lý bucket


### Quản lý object (folder, file)

#### Lấy, tạo mới, xóa


#### Danh sách file


#### Quản lý bucket policy


<hr class="rounded">
### Tài liệu tham khảo


<hr class="rounded">
### Các tính năng khác