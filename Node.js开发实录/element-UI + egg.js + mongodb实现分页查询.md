（效果呈现gif）

（MongoDB分页原理）
db.getCollection('job').find({
  status: {
    '$in': ['PUBLISH']
  },
  type: {
    '$in': ['SPIDER']
  },
  recoredTime: {
    '$ne': new Date('2019-09-28')
  },
  star: true
}).sort('recoredTime':true)

常用方式：skip跨越记录查询
优化方式：以_id作为条件进行查询

（实现思路和关键代码）
1. 监听搜索面板条件
2. 获取总记录数
3. 根据总记录数、每页记录数、当前选中页数来实例化分页器
4. 获取当前页的数据，并记录firstId/lastId
3. 向后翻页时，通过
   find({'$gt': lastId}).sort({recoredTime: 1}).limit(10)
   向前翻页时，通过
   find({'$lt': firstId}).sort({recoredTime: 1}).limit(10)