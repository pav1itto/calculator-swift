// `Calculator` represents a basic calculator that can perform arithmetic operations on numbers.
//
// - Functions:
//   - add: Adds two numbers and returns the result.
//   - subtract: Subtracts the second number from the first number and returns the result.
//   - multiply: Multiplies two numbers and returns the result.
//   - divide: Divides the first number by the second number and returns the result.
class Calculator {

    // Adds two numbers and returns the result.
    //
    // - Parameters:
    //   - num1: The first number.
    //   - num2: The second number.
    //
    // - Returns: The sum of `num1` and `num2`.
    func add(_ num1: Double, _ num2: Double) -> Double {
        return num1 + num2
    }

    // Subtracts the second number from the first number and returns the result.
    //
    // - Parameters:
    //   - num1: The first number.
    //   - num2: The second number.
    //
    // - Returns: The difference between `num1` and `num2`.
    func subtract(_ num1: Double, _ num2: Double) -> Double {
        return num1 - num2
    }

    // Multiplies two numbers and returns the result.
    //
    // - Parameters:
    //   - num1: The first number.
    //   - num2: The second number.
    //
    // - Returns: The product of `num1` and `num2`.
    func multiply(_ num1: Double, _ num2: Double) -> Double {
        return num1 * num2
    }

    // Divides the first number by the second number and returns the result.
    //
    // - Parameters:
    //   - num1: The first number.
    //   - num2: The second number.
    //
    // - Returns: The quotient of `num1` divided by `num2`.
    // - Throws: `CalculatorError.divisionByZero` if `num2` is zero.
    func divide(_ num1: Double, _ num2: Double) throws -> Double {
        guard num2 != 0 else {
            throw CalculatorError.divisionByZero
        }
        return num1 / num2
    }

    enum CalculatorError: Error {
        case divisionByZero
    }
}

// Example usage of the Calculator class:

// Initialize the Calculator environment
let calculator = Calculator()

// Perform addition
let sum = calculator.add(5, 3)
print("Sum: \(sum)")

// Perform subtraction
let difference = calculator.subtract(5, 3)
print("Difference: \(difference)")

// Perform multiplication
let product = calculator.multiply(5, 3)
print("Product: \(product)")

// Perform division
do {
    let quotient = try calculator.divide(5, 3)
    print("Quotient: \(quotient)")
} catch Calculator.CalculatorError.divisionByZero {
    print("Division by zero is not allowed.")
}
