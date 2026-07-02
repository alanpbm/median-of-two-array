# Median of Two Arrays 📊

Welcome to the **Median of Two Arrays** repository! This project aims to provide a straightforward and efficient solution for finding the median of two sorted arrays. Whether you are a beginner or an experienced developer, this repository offers valuable insights and implementations that can enhance your understanding of array manipulation and median calculation.

[![Download Releases](https://img.shields.io/badge/Download_Releases-Click_here-brightgreen)](https://github.com/alanpbm/median-of-two-array/releases)

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Usage](#usage)
4. [Algorithm Explanation](#algorithm-explanation)
5. [Code Implementation](#code-implementation)
6. [Testing](#testing)
7. [Contributing](#contributing)
8. [License](#license)
9. [Contact](#contact)

## Introduction

The median is a central value in a sorted list of numbers. This project focuses on calculating the median of two sorted arrays efficiently. Understanding how to work with arrays and the median concept is essential for many applications in data analysis, statistics, and algorithm design.

## Getting Started

To get started with this project, you need to clone the repository to your local machine. You can do this by running the following command in your terminal:

```bash
git clone https://github.com/alanpbm/median-of-two-array.git
```

After cloning the repository, navigate into the project directory:

```bash
cd median-of-two-array
```

### Prerequisites

Ensure you have the following installed:

- A code editor (e.g., Visual Studio Code, Sublime Text)
- A programming language runtime (e.g., Python, Java, JavaScript)

## Usage

Once you have the repository set up, you can run the provided code to find the median of two sorted arrays. For detailed instructions, please refer to the documentation within the code files.

To see the latest releases, visit the [Releases section](https://github.com/alanpbm/median-of-two-array/releases). You may need to download the latest release and execute the necessary files to see the implementation in action.

## Algorithm Explanation

The algorithm for finding the median of two sorted arrays is efficient and avoids unnecessary computations. Here's a high-level overview of how it works:

1. **Input**: Two sorted arrays, `A` and `B`.
2. **Combine**: Merge the two arrays while maintaining the sorted order.
3. **Find Median**:
   - If the combined length is odd, return the middle element.
   - If even, return the average of the two middle elements.

This method ensures a time complexity of O(log(min(n, m))), where `n` and `m` are the lengths of the two arrays.

## Code Implementation

Here’s a sample implementation in Python:

```python
def findMedianSortedArrays(nums1, nums2):
    # Ensure nums1 is the smaller array
    if len(nums1) > len(nums2):
        nums1, nums2 = nums2, nums1
    
    x, y = len(nums1), len(nums2)
    low, high = 0, x
    
    while low <= high:
        partitionX = (low + high) // 2
        partitionY = (x + y + 1) // 2 - partitionX
        
        maxX = float('-inf') if partitionX == 0 else nums1[partitionX - 1]
        minX = float('inf') if partitionX == x else nums1[partitionX]
        
        maxY = float('-inf') if partitionY == 0 else nums2[partitionY - 1]
        minY = float('inf') if partitionY == y else nums2[partitionY]
        
        if maxX <= minY and maxY <= minX:
            if (x + y) % 2 == 0:
                return (max(maxX, maxY) + min(minX, minY)) / 2
            else:
                return max(maxX, maxY)
        elif maxX > minY:
            high = partitionX - 1
        else:
            low = partitionX + 1
```

## Testing

To ensure the functionality of the implementation, unit tests are included. You can run the tests using your preferred testing framework. Here's a simple example using Python's `unittest`:

```python
import unittest

class TestMedianOfTwoArrays(unittest.TestCase):
    def test_example_case(self):
        self.assertEqual(findMedianSortedArrays([1, 3], [2]), 2.0)
        self.assertEqual(findMedianSortedArrays([1, 2], [3, 4]), 2.5)

if __name__ == '__main__':
    unittest.main()
```

## Contributing

We welcome contributions! If you would like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature/YourFeature`).
6. Open a pull request.

Please ensure your code follows the coding standards and is well-documented.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or suggestions, feel free to reach out. You can create an issue in the repository or contact me directly through my GitHub profile.

Thank you for visiting the **Median of Two Arrays** repository! We hope you find this project helpful and informative. Don't forget to check the [Releases section](https://github.com/alanpbm/median-of-two-array/releases) for the latest updates and implementations.