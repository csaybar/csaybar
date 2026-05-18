```cpp
#include <memory>

struct Us {
    ~Us();
};

Us::~Us() {}

int main() {
    auto her = std::weak_ptr<Her>{};

    if (auto she = her.lock()) {
        she->read(this_letter);
    }

    return 0;
}
```
