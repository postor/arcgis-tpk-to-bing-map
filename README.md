# arcgis-tpk-to-bing-map

当然除了bing地图，google地图、leaflet等也都能用 | besides bing map, tiles can also be used in google map, leaflet etc.

## 步骤 | steps

### 1 从arcgis导出tpk文件 | export tpk from arcgis

http://desktop.arcgis.com/zh-cn/arcmap/10.3/map/working-with-arcmap/how-to-create-a-tile-package.htm

http://desktop.arcgis.com/zh-cn/arcmap/10.3/tools/data-management-toolbox/export-tile-cache.htm

### 2 利用tpkutils生成图片 | generate tile images from tpk

https://github.com/consbio/tpkutils

- install python
- install pip
- install tpkutils
- tpk export disk test.tpk ./tiles

### 3 将生成的贴图应用到bing地图 | apply tiles on bing map

添加一个TileLayer应用之前生成的图片 | insert a TileLayer using images generated from tpk

```
var tpkTileLayer = new Microsoft.Maps.TileLayer({
    mercator: new Microsoft.Maps.TileSource({
        uriConstructor: '/tiles/{zoom}/{x}/{y}.png'
    })
});
map.layers.insert(tpkTileLayer);
```

## 测试结果 | show result

```
npm install
npm run start # simply http-server
```
http://localhost:8080/
