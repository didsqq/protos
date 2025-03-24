protoc -I proto proto/sso/sso.proto --go_out=./gen/go --go_opt=paths=source_relative --go-grpc_out=./gen/go/ --go-grpc_opt=paths=source_relative

task generate

protoc -I proto proto/sso/sso.proto - Говорит компилятору, что файлы .proto находятся в папке proto, и используется файл proto/sso/sso.proto
--go_out=./gen/go --go_opt=paths=source_relative - Указывает, где будет сгенерирован код, Параметр paths=source_relative гарантирует, что 
структура файлов будет отражать структуру исходных файлов .proto.

--go-grpc_out=./gen/go/ --go-grpc_opt=paths=source_relative
Указывает, что сгенерированный код для gRPC будет помещен в ту же директорию.
Параметр paths=source_relative также гарантирует правильную структуру.

sso.pb.go — Этот файл содержит структуры данных (сообщения) для всех типов, определённых в .proto файле.
sso_grpc.pb.go — Этот файл содержит сгенерированные gRPC сервисы и соответствующие интерфейсы для их реализации.