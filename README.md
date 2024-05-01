![17671-kyphosis](https://github.com/1varma/Kyphosis-Child-Disease-Project---Decision-Tree/assets/39651154/dc3a1040-9b0b-427d-80a4-ecb4012abddb)


# Data on Children who have had Corrective Spinal Surgery

## Description

The `kyphosis` data frame consists of 81 rows and 4 columns, representing data on children who have had corrective spinal surgery.

## Usage

`kyphosis`

## Format

This data frame contains the following columns:

- **Kyphosis**: a factor with levels `absent` and `present`, indicating if a kyphosis (a type of deformation) was present after the operation.
- **Age**: age of the child in months.
- **Number**: the number of vertebrae involved.
- **Start**: the number of the first (topmost) vertebra operated on.

## Source

John M. Chambers and Trevor J. Hastie eds. (1992) Statistical Models in S, Wadsworth and Brooks/Cole, Pacific Grove, CA.

## Examples

```r
fit <- rpart(Kyphosis ~ Age + Number + Start, data = kyphosis)
fit2 <- rpart(Kyphosis ~ Age + Number + Start, data = kyphosis,
              parms = list(prior = c(0.65, 0.35), split = "information"))
fit3 <- rpart(Kyphosis ~ Age + Number + Start, data = kyphosis,
              control = rpart.control(cp = 0.05))
par(mfrow = c(1,2), xpd = TRUE)
plot(fit)
text(fit, use.n = TRUE)
plot(fit2)
text(fit2, use.n = TRUE)
```

This Readme provides an overview of the `kyphosis` dataset, including its structure, usage, format, and source. Additionally, it includes example code snippets demonstrating how to fit regression trees (`rpart`) using this dataset.
