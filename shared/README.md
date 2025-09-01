# Surreal Number Comparison Analysis Component

This directory contains a reusable LaTeX component for analyzing surreal number comparisons. The component provides a tabular format that shows the step-by-step process of determining whether one surreal number is greater than or equal to another.

## Files

- `surreal-comparison.tex` - The main component file containing LaTeX macros for comparison analysis

## Usage

### Requirements

Your LaTeX document must include the following packages before importing this component:
```latex
\usepackage{amsmath}
\usepackage{array}
\usepackage{booktabs}
```

### Including the Component

Add this line to your LaTeX document (adjust path as needed):
```latex
\input{../shared/surreal-comparison.tex}
```

### Main Command

The primary command provided by this component is:

```latex
\surrealComparisonAnalysis{x_notation}{x_left}{x_right}{y_notation}{y_left}{y_right}{conclusion}
```

**Parameters:**
- `x_notation`: The mathematical notation for the first surreal number (e.g., `\frac{1}{2}`)
- `x_left`: The left set of the first surreal number (e.g., `0` for a set containing 0, empty for empty set)
- `x_right`: The right set of the first surreal number  
- `y_notation`: The mathematical notation for the second surreal number
- `y_left`: The left set of the second surreal number
- `y_right`: The right set of the second surreal number
- `conclusion`: The final result (e.g., `$\checkmark$ True` or `$\times$ False`)

### Examples

#### Simple comparison (½ ≥ 0):
```latex
\surrealComparisonAnalysis{\frac{1}{2}}{0}{1}{0}{}{}{$\checkmark$ True}
```

#### More complex comparison (1 ≥ ½):
```latex
\surrealComparisonAnalysis{1}{0}{}{{\frac{1}{2}}}{0}{1}{$\checkmark$ True}
```

### How It Works

The component creates a structured table showing:

1. **Step 1**: Checks that no element in the left set of the first number is ≥ the second number
2. **Step 2**: Checks that no element in the right set of the second number is ≤ the first number
3. **Conclusion**: The final result based on both conditions

This follows the formal definition of surreal number ordering: x ≤ y if and only if:
- No element of L_y is ≥ x, AND  
- No element of R_x is ≤ y

## Mathematical Background

The component is based on Conway's definition of surreal numbers where each number is represented as {L|R} with L being the left set and R being the right set. The ordering relation is defined recursively, making step-by-step analysis essential for understanding complex comparisons.

## Customization

The component provides helper functions that can be modified:
- `\surrealAnalyzeLeft` - Analyzes left set conditions
- `\surrealAnalyzeRight` - Analyzes right set conditions  
- `\surrealResultLeft` - Determines results for left set checks
- `\surrealResultRight` - Determines results for right set checks

You can extend these functions to handle more complex cases or provide more detailed analysis for specific scenarios.