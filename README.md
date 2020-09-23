# Golang struct generator for PostgreSQL

## Install
```
go get -u github.com/fgituser/go-pg-generator
```

## Exmaple

```
✗ go-pg-generator --server localhost --port 5555 --user postgres --password postgres --database=bsk --tables goose_db_version --ssl disable

type GooseDbVersion struct {
        ID int32 `db:"id"` // sqltype: int4
        VersionID int64 `db:"version_id"` // sqltype: int8
        IsApplied bool `db:"is_applied"` // sqltype: bool
        Tstamp null.Time `db:"tstamp"` // sqltype: timestamp
}

```

## Help
```
Usage:
  go-pg-generator [OPTIONS]

Application Options:
  -s, --server=         Server name or IP address (default: 127.0.0.1)
  -p, --port=           Port (default: 5432)
  -u, --user=           Database user.
  -w, --password=       Database password.
  -d, --database=       Database name.
  -t, --tables=         Tables to export.
      --ssl=            SSL mode (require|verify-full|verify-ca|disable) (default: disable)
  -f, --file-per-table  Save each structure to its own .go file.
      --package=        Package name for generated files.

Help Options:
  -h, --help            Show this help message
```
