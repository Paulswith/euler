The project is for [euler-algorithm](https://www.projecteuler.net/archives) resolved code write by [rust](https://www.rust-lang.org/), as personal algorithm learning project
In my code, I will show the problem, and my personal problem solving
```rust
/*
Multiples of 3 and 5
- Problem 1
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
Find the sum of all the multiples of 3 or 5 below 1000.
------------------------------------------------------------------------------------------------
** 解:
[1 - 1000)内的倍数之和, 可以用等差数列的方式的求和方法来处理, 3和5是两个等差数列, 最后Sn_3 + Sn_5
*/
pub fn entry() {
    let range_max = 1000;
    let multiple_3 = 3;
    let multiple_5 = 5;
    let sum = sum_multiple(multiple_3, range_max) + sum_multiple(multiple_5, range_max);
    assert_eq!(sum, test(multiple_3, multiple_5, range_max));
    println!("sum of all the multiples of 3 or 5 below 1000, result is {}", sum);
}

#[warn(dead_code)]
fn sum_multiple(multiple: u32, in_range_max: u32) -> u32 {
    let n = (in_range_max - 1) / multiple; // - 1, cause [1, 1000)
    let a_1 = 1 * multiple;
    let a_n = n * multiple;
    (a_1 + a_n) / 2 * n   // Sn = ((a1 + an) / 2) * n
}
```

improve together