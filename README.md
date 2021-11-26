# This project is for generating a jar for a proto file using MAVEN
## This project is just personal

In this case I use the annotations for swagger in order to generate 
a swagger file with more information as yhe host for example

All the credit to *grpc-ecosystem/grpc-gateway* for the proto file annotations.proto

All the documentation about the swagger annotations for a proto file are in the next links

#### Full documentation (In this link is also a way for generating the jar using protoc and go, just need add the --java_out flag)

https://github.com/grpc-ecosystem/grpc-gateway/

#### Example of all the options for swagger
https://github.com/grpc-ecosystem/grpc-gateway/blob/ab0345bb328757bfef2f3d7d4e642e182eb985b9/examples/proto/examplepb/a_bit_of_everything.proto

#### The locatios of the proto files
https://github.com/grpc-ecosystem/grpc-gateway/tree/master/protoc-gen-openapiv2/options

For this project I merge teh annotations and the openapiv2 proto file in just 
1 file, the annotations.proto file. Just for fun

In order to use in another project as a dependency we need to add the next things

`<dependency>
   <groupId>com.github.carlos-contreras-ruiz</groupId>
   <artifactId>swagger-annotations</artifactId>
   <version>1.0-SNAPSHOT</version>
</dependency>`

Of course the groupId,artifactId and version will depend on the data that the project has 

In the proto file that we need to add the swagger options we need to add

##### import "com/github/carlos-contreras-ruiz/annotations.proto";

##### option (grpc.gateway.protoc_gen_openapiv2.options.openapiv2_swagger) = {
#####    host:"our-url.com"
##### };

With all that we are ready to generate a Swagger file more detail with maven
