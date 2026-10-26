```cpp
#include <generator>
#include <memory>
#include <type_traits>

struct Moment {
    Moment() = default;
    Moment(const Moment&) = delete;
};

static_assert(!std::is_copy_constructible_v<Moment>);

std::generator<const Moment&> after() {
    for (;;) co_yield Moment{};
}

int main() {
    auto then = std::make_unique<Moment>();
    then.reset();

    auto rest = after();
}
```
