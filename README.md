# 2024.3.26
1. 性能如何，有没有测试数据。TPC-H
2. 关键特性是什么？
# bordkv

bordkv is another bitcask like kv storage in C++17.

usage:

```c++
#include <string>

#include <easylogging++.h>

#include "bordkv/kv.h"

using namespace bordkv;

INITIALIZE_EASYLOGGINGPP

int main(int argc,char* argv[]) {
    std::string dir = "./tmp/";
    Option option { 1024 };
    
    BordKV kv = BordKV::Create(dir, option);
    auto option = kv.Get("key");
    auto future = kv.Write("key", "value");
    auto future1 = kv.Delete("key");

    return 0;
}
```