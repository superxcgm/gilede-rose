# Gilded Rose （Not Gilede Rose!!!）

## Tasking

1. 商品有SellIn（sell in的驼峰形式），Quality属性
2. 商品初始化时，价格不能低于0
3. 商品初始化时，价格不能高于50
4. 普通商品，每过1天，价值会下滑1点
5. 普通商品过了保质期，价值每天下滑2点（双倍）
6. 普通商品在价值归0之后，不会再下滑（价值永远不会小于0）
7. 后台门票在演出的前10天，价值每天上升2点
8. 后台门票在演出的前5天，价值每天上升3点
9. 后台门票的价格达到50之后， 不会再上升（价值不会超过50）
10. 后台门票在过了演出日，价值变成0

后台门票在前10天之前的价值变化在需求中未提及，属于未定义行为。
该系统如何交互在需求中未提及，这里不做实现。

## Build

### Prerequisite
1. cmake INSTALLED
2. conan INSTALLED

### Build
```shell script
# install dependency
cd test
mkdir build && cd build
conan install ..

# build
cd ../..
mkdir cmake-build-debug && cd cmake-build-debug 
cmake --build .

# run test
./test/tests
```