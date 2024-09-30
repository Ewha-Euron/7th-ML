## Week 2 정리

### 2.2
scikit-learn 사용법 익히기
import
sklearn.datasets : sklearn의 data 생성
sklearn.model_selection : 데이터 split, best hyperparameter 찾기

ex. train_test_split()
> sklearn.model_selection.train_test_split(*arrays, test_size=None, train_size=None, random_state=None, shuffle=True, stratify=None)

sklearn.tree : sklearn tree 알고리즘 관련
sklearn.metrics : 정확도 등의 성능 평가와 관련

ex. accuracy_score()

### 2.3
2 Supervised Learning Model (Estimator)  
1. Classification -> Classifier
2. Regression -> Regressor

### 2.4 
교차 검증
1. K-Fold validation
2. StratifiedKFold

교차 검증을 편리하게 할 수 있는 API
cross_val_score()
> cross_val_score(estimator, X, y=None, \*, groups=None, scoring=None, cv=None, n_jobs=None, verbose=0, fit_params=None, params=None, pre_dispatch='2*n_jobs', error_score=nan)


GridSearchCV()
각각의 hyperparameters 한 번에 
> GridSearchCV(estimator, param_grid, *, scoring=None, n_jobs=None, refit=True, cv=None, verbose=0, pre_dispatch='2*n_jobs', error_score=nan, return_train_score=False)

\**
cv_results.params 
cv_results.mean_test_score
cv_results.rank_test_score
cv_results.split0_test_score
cv_results.split1_test_score
cv_results.split2_test_score
best_params
best_score
\**

### 2.5
- 레이블 인코딩 : 선형 회귀나 ML에서는 비추천
- One-Hot Encoding 
fit(), transform()을 사용하여 데이터 변환
fit_transform()을 사용할 시에는 주의해야 한다. 기왕이면 그냥 따로 하는 것이 좋아 보인다. 

### 2.6
- PassengerId: A unique identifier for each passenger.
- Survived: This indicates whether the passenger survived (1) or not (0).
- Pclass: The passenger's class (1st, 2nd, or 3rd class).
- Name: The name of the passenger.
- Sex: The gender of the passenger (male or female).
- Age: The age of the passenger in years. Some values are missing in the dataset.
- SibSp: Number of siblings or spouses the passenger had aboard the Titanic.
- Parch: Number of parents or children the passenger had aboard the Titanic.
- Ticket: The ticket number of the passenger.
- Fare: The amount of money the passenger paid for the ticket.
- Cabin: The cabin number where the passenger stayed. Many values are missing in this column.
- Embarked: The port where the passenger boarded the Titanic. The three values are:
C = Cherbourg
Q = Queenstown
S = Southampton

## 3
- $$\begin{bmatrix}
\text{True Positive (TP)} & \text{False Positive (FP)} \\
\text{False Negative (FN)} & \text{True Negative (TN)}
\end{bmatrix}
$$

- $$\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}
$$

- $$\text{Precision} = \frac{TP}{TP + FP}
$$
- $$\text{Recall} = \frac{TP}{TP + FN}
$$
