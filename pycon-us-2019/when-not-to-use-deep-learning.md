# Put down the deep learning: When not to use neural networks and what to do instead

https://us.pycon.org/2019/schedule/presentation/200/

- we don't even have a good understanding of how some models work
- you sometimes just run a bunch of stuff and observe what works
- also, training models is pretty expensive
- use deep learning if
  - a human can do it in less than a second (otherwise the problem is too complex)
  - you have high tolerance for error
    - humans use silhouettes, computers use pixels, so they can be fooled by texture
  - if you don't need to explain yourself (so not in finance)
  - you have >5000 per class of labelled data (or you can use transfer learning)
- deep learning needs a lot of time, a lot of money, a lot of data
  - it's the most powerful, though

## Alternative 1: Regression

The most interpretable.

- you pick the family of function you use to model data (such as linear)
- many models exist already, and we have a good understanding of them
- this is very fast
- doesn't need lots of data
- it's more work to prepare the data
- mixed effects regression is a useful go-to model, useful for Simpson's paradox
  - it's in statsmodels as `statsmodels.formula.api.mixedlm`

## Alternative 2: Trees

The user friendliest.

- people use random forests, which is lots of decision trees linked together
  - two thirds of kaggle winners use them
- you can use `xgboost`, `lightgbm`, `catboost`
  - xgboost's defaults are pretty good
- easy to overfit though, you could have one leaf per data point, you gotta trim that
- less easy to interpret than regression

## Alternative 3: Distance-based Models

The most lightweight.

- such as K-nearest neighbors
- support vector machines works with 4 points, it's 10x faster than deep learning, accuracy is okayish
  - scikit-learn has it in `sklearn.svk`
