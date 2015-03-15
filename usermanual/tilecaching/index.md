# Tile Caches #

Tile is a pre-rendered georeferenced map image. MapSurfer.NET framework has a built-in tile caching mechanism which allows to deliver higher performance and lower loading of TMS and WMTS services. The framework supports the following cache types:

- [AzureBlobStorage](usermanual/tilecaching/azurestorage.md)
- [BerkeleyDB](usermanual/tilecaching/berkeleydb.md)
- [Cassandra](usermanual/tilecaching/cassandra.md)
- [CouchDB](usermanual/tilecaching/couchdb.md)
- [DefaultDisk](usermanual/tilecaching/defaultdisk.md)
- [Dropbox](usermanual/tilecaching/dropbox.md)
- [GoogleDisk](usermanual/tilecaching/googledisk.md)
- [Hypertable](usermanual/tilecaching/hypertable.md)
- [KosmosnimkiDisk](usermanual/tilecaching/kosmosnimkidisk.md)
- [MaemoMapperSQLite](usermanual/tilecaching/maemomappersqlite.md)
- [MBTiles](usermanual/tilecaching/mbtiles.md)
- [Memcached](usermanual/tilecaching/memcached.md)
- [MetatileDisk](usermanual/tilecaching/metatiledisk.md)
- [MongoDB](usermanual/tilecaching/mongodb.md)
- [QuadkeyDisk](usermanual/tilecaching/quadkeydisk.md)
- [Redis](usermanual/tilecaching/redis.md)
- [SasplanetDisk](usermanual/tilecaching/sasplanetdisk.md)
- [YandexDisk](usermanual/tilecaching/yandexdisk.md)


> %!IMPORTANT NOTE !% MapSurfer.NET provides an API to develop a custom tile cache provider which can be implemented and integrated into the framework through a [plugin](/devmanual/plugins) system.