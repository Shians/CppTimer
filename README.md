# CppTimer
Header only `Timer` class based on C++11 `std::chrono`. Simply download the `Timer.hpp` file and include it where required.

## Example

```
#include <iostream>
#include <thread>
#include <chrono>
#include "Timer.hpp"

int main() {
    Timer timer;
    timer.start();

    std::this_thread::sleep_for(std::chrono::seconds(3)); // sleep for 3 seconds

    std::cout << "microseconds elapsed: " << timer.microseconds_elapsed() << "\n";
    std::cout << "milliseconds elapsed: " << timer.milliseconds_elapsed() << "\n";
    std::cout << "seconds elapsed: " << timer.seconds_elapsed() << "\n";
    return 0;
};
```

## Usage

Timer has the following methods

| Method | Description|
| ------------- |:-------------|
| start() | Start the timer |
| reset() | Reset the timer (alias for start) |
| nanoseconds_elapsed() | Returns nanoseconds elapsed since timer started |
| microseconds_elapsed() | Returns microseconds elapsed since timer started |
| milliseconds_elapsed() | Returns milliseconds elapsed since timer started |
| seconds_elapsed() | Returns seconds elapsed since timer started |
| minutes_elapsed() | Returns minutes elapsed since timer started |
| hours_elapsed() | Returns hours elapsed since timer started |

The return type of all `xxx_elapsed()` functions is `unsigned long`.

**Be careful with using `nanoseconds` and `microseconds` as they can easily overflow.**
