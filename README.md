# gRPC example

This is a simple example of a gRPC server, it was built to be used as an example only and to learn the basics.

## Dependencies

- [gRPC](https://grpc.io/docs/languages/go/quickstart/)
- [evans](https://github.com/ktr0731/evans)

### Database

- [sqlite3](https://www.tutorialspoint.com/sqlite/sqlite_installation.htm)

Create the table with:

```sql
create table categories(id string,  name string,  description string);
```

## How to run

1. Run the server

```bash
go run cmd/grpcServer/main.go
```

2. Run the evans

```bash
evans -r repl
```

3. Inside evans, go to the pb package and on `CategoryService`:

```bash
package pb
service CategoryService
```

4. Call any method you want, e.g. `GetCategory`:

```bash
pb.CategoryService@127.0.0.1:50051> call GetCategory
id (TYPE_STRING) => 8b1d34ca-9805-48ba-a6ca-a81d10abe1f4
{
  "category": {
    "description": "cat 1 desc",
    "id": "8b1d34ca-9805-48ba-a6ca-a81d10abe1f4",
    "name": "cat 1"
  }
}
```
