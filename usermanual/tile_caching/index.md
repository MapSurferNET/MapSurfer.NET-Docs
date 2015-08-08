# Tile Cache Storages

Tile is a pre-rendered georeferenced map image. MapSurfer.NET framework has a built-in tile caching mechanism which allows to deliver higher performance and lower loading of TMS and WMTS services. The framework supports the following cache types:

- [AzureBlobStorage](usermanual/tile_caching/azurestorage.md)
- [BerkeleyDB](usermanual/tile_caching/berkeleydb.md)
- [Cassandra](usermanual/tile_caching/cassandra.md)
- [CouchDB](usermanual/tile_caching/couchdb.md)
- [DefaultDisk](usermanual/tile_caching/defaultdisk.md)
- [Dropbox](usermanual/tile_caching/dropbox.md)
- [GoogleDisk](usermanual/tile_caching/googledisk.md)
- [Hypertable](usermanual/tile_caching/hypertable.md)
- [KosmosnimkiDisk](usermanual/tile_caching/kosmosnimkidisk.md)
- [MaemoMapperSQLite](usermanual/tile_caching/maemomappersqlite.md)
- [MBTiles](usermanual/tile_caching/mbtiles.md)
- [Memcached](usermanual/tile_caching/memcached.md)
- [MetatileDisk](usermanual/tile_caching/metatiledisk.md)
- [MongoDB](usermanual/tile_caching/mongodb.md)
- [QuadkeyDisk](usermanual/tile_caching/quadkeydisk.md)
- [Redis](usermanual/tile_caching/redis.md)
- [SasplanetDisk](usermanual/tile_caching/sasplanetdisk.md)
- [YandexDisk](usermanual/tile_caching/yandexdisk.md)


> %!IMPORTANT NOTE !% MapSurfer.NET provides an API to develop a custom tile cache provider which can be implemented and integrated into the framework through a [plugin](/devmanual/plugins/index.md) system.


### See also

[Generating Tile Cache using MapSurfer.NET Studio](/usermanual/tools/msnstudio/export-tile-cache.md)
