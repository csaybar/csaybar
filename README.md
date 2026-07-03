```cpp
#include <ranges>
#include <limits>

struct Her {
    struct Light {} light;
    struct Calm  {} calm;
    struct Music {} music;
};

static_assert(std::numeric_limits<double>::has_infinity);

int main() {
    auto [light, calm, music] = Her{};

    for (auto reason : std::views::iota(1)) {
        ;
    }
}
```
