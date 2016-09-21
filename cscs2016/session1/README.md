# Hello World

* Buuh
* YAya
```
void wait_for_latch(hpx::lcos::local::latch& l)
{
    l.count_down_and_wait();
}

int main()
{
    // Spawn a couple of threads
    hpx::lcos::local::latch l(num_threads+1);

    std::vector<hpx::future<void> > results;
    results.reserve(num_threads);

    for (int i = 0; i != num_threads; ++i)
        results.push_back(hpx::async(&wait_for_latch, std::ref(l)));
}
```
---

# More

```
int main()
{}
```
