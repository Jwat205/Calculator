# ESEP Grade Calculator

A simple utility to calculate course grades.

Requires Go 1.24+.

## Usage

```go
calc := esepunittests.NewGradeCalculator()
calc.AddGrade("homework 1", 100, esepunittests.Assignment)
calc.AddGrade("exam 1", 95, esepunittests.Exam)
calc.AddGrade("essay 1", 91, esepunittests.Essay)
calc.GetFinalGrade() // "A"
```

Final grade = 50% assignments + 35% exams + 15% essays (category averages), letter grade A (90+), B (80+), C (70+), D (60+), otherwise F.

Each category needs at least one grade before calling `GetFinalGrade`.

## Tests

```
cd grade_calculator/
go test ./...
go test -coverprofile=coverage.txt ./...
```