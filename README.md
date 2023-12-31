# transposeMatrix
## Matrix Transposition in Swift

This Swift code demonstrates how to transpose a 2D matrix.

## Code Explanation

```swift
func transposeMatrix(_ matrix: [[Int]]) -> [[Int]] {
    // Check if the matrix is empty, and return an empty matrix if it is.
    guard !matrix.isEmpty else { return [] }

    // Get the number of rows and columns in the original matrix.
    let numRows = matrix.count
    let numCols = matrix[0].count

    // Initialize the result matrix with dimensions swapped.
    var result = Array(repeating: Array(repeating: 0, count: numRows), count: numCols)

    // Iterate through the original matrix and populate the result matrix with transposed values.
    for i in 0..<numRows {
        for j in 0..<numCols {
            result[j][i] = matrix[i][j]
        }
    }

    return result
}

// Define an original matrix.
let originalMatrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

// Call the transposeMatrix function to get the transposed matrix.
let transposedMatrix = transposeMatrix(originalMatrix)

// Print the transposed matrix.
for row in transposedMatrix {
    print(row)
}


==========================
# Matrix Transposition in Swift

This Swift code demonstrates how to transpose a 2D matrix.

## Code Explanation

```swift
func transposeMatrix(_ matrix: [[Int]]) -> [[Int]] {
    // Check if the matrix is empty or has empty rows, and return an empty matrix if so.
    guard !matrix.isEmpty, !matrix[0].isEmpty else { return [] }

    let numRows = matrix.count
    let numCols = matrix[0].count

    // Use a compact map to create the transposed matrix directly.
    let result = (0..<numCols).map { j in
        (0..<numRows).map { i in matrix[i][j] }
    }

    return result
}

// Define an original matrix.
let originalMatrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

// Call the `transposeMatrix` function to get the transposed matrix.
let transposedMatrix = transposeMatrix(originalMatrix)

// Print the transposed matrix.
for row in transposedMatrix {
    print(row)

Simplified Matrix Initialization:

Used a more concise approach to initialize the result matrix using a nested map function. This eliminates the need for explicit loops.
Removed Unnecessary Type Annotations:

Removed explicit type annotations ([[Int]] and [Int]) during the matrix initialization for brevity, as Swift can infer the types.
Eliminated Mutable Variable:

Since the result matrix is now directly created, there's no need for a mutable variable.


