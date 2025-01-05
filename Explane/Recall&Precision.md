# Precision vs Recall

Precision and Recall are two key metrics for evaluating the performance of classification models. In this file, we'll explain their differences, applications, and usage with examples.

---

## 1. **Precision:**

### **Definition:**
Precision is the ratio of correctly predicted positive observations to the total predicted positive observations.

### **Formula:**
\[
\text{Precision} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Positives (FP)}}
\]

### **Goal:**
To measure how many of the positive predictions made by the model are actually correct.

### **Application:**
Used when the cost of False Positives (FP) is high.

**Example:**
In Spam Detection: 
- If an important email is mistakenly marked as spam, it could lead to missing critical information. High precision is crucial in such cases.

### **Python Example:**
```python
from sklearn.metrics import precision_score

# Actual and predicted values
y_true = [0, 1, 1, 0, 1]  # Ground truth
y_pred = [0, 1, 0, 0, 1]  # Predictions

# Calculate Precision
precision = precision_score(y_true, y_pred)
print("Precision:", precision)
```

---

## 2. **Recall (Sensitivity):**

### **Definition:**
Recall is the ratio of correctly predicted positive observations to all the actual positive observations.

### **Formula:**
\[
\text{Recall} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Negatives (FN)}}
\]

### **Goal:**
To measure how many of the actual positive cases are correctly identified by the model.

### **Application:**
Used when the cost of False Negatives (FN) is high.

**Example:**
In Cancer Detection: 
- If a patient with cancer is incorrectly diagnosed as healthy, critical treatment might be missed. High recall is crucial in such cases.

### **Python Example:**
```python
from sklearn.metrics import recall_score

# Actual and predicted values
y_true = [0, 1, 1, 0, 1]  # Ground truth
y_pred = [0, 1, 0, 0, 1]  # Predictions

# Calculate Recall
recall = recall_score(y_true, y_pred)
print("Recall:", recall)
```

---

## 3. **Difference Between Precision and Recall:**

| **Aspect**         | **Precision**                                       | **Recall**                                         |
|---------------------|-----------------------------------------------------|---------------------------------------------------|
| **Focus**          | Accuracy of positive predictions                    | Coverage of actual positive cases                |
| **Optimizes For**  | Reducing False Positives (FP)                       | Reducing False Negatives (FN)                    |
| **When To Use**    | When the cost of False Positives is high            | When the cost of False Negatives is high         |

---

## 4. **F1-Score:**

### **Definition:**
F1-Score is the harmonic mean of Precision and Recall, used to balance both metrics.

### **Formula:**
\[
\text{F1-Score} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}
\]

### **Python Example:**
```python
from sklearn.metrics import f1_score

# Actual and predicted values
y_true = [0, 1, 1, 0, 1]  # Ground truth
y_pred = [0, 1, 0, 0, 1]  # Predictions

# Calculate F1-Score
f1 = f1_score(y_true, y_pred)
print("F1-Score:", f1)
```

---

## 5. **Summary:**
- **Precision:** Focuses on the accuracy of positive predictions.
- **Recall:** Focuses on identifying all actual positive cases.
- **F1-Score:** Balances Precision and Recall.

Choosing the right metric depends on the problem and the cost of errors.


--

## persian 

----

# Precision vs Recall

Precision و Recall دو معیار کلیدی برای ارزیابی عملکرد مدل‌های دسته‌بندی (Classification) هستند. در این فایل، به همراه مثال‌ها، تفاوت‌ها، کاربردها و نحوه استفاده از این دو معیار بررسی می‌شود.

---

## 1. **Precision (دقت):**

### **تعریف:**
Precision نسبت تعداد پیش‌بینی‌های درست به تمام مواردی است که به عنوان مثبت پیش‌بینی شده‌اند.

### **فرمول:**
\[
\text{Precision} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Positives (FP)}}
\]

### **هدف:**
از بین تمام پیش‌بینی‌های مثبت مدل، چه تعداد درست بوده‌اند.

### **کاربرد:**
زمانی که هزینه مثبت اشتباه (**False Positive**) بالا باشد. 

**مثال:**
در تشخیص هرزنامه (Spam Detection): 
- اگر یک ایمیل مهم به اشتباه اسپم تشخیص داده شود، ممکن است پیام مهمی از دست برود. بنابراین دقت بالا در اینجا اهمیت دارد.

### **مثال کد در پایتون:**
```python
from sklearn.metrics import precision_score

# مقادیر واقعی و پیش‌بینی‌شده
y_true = [0, 1, 1, 0, 1]  # مقادیر واقعی
y_pred = [0, 1, 0, 0, 1]  # مقادیر پیش‌بینی‌شده

# محاسبه Precision
precision = precision_score(y_true, y_pred)
print("Precision:", precision)
```

---

## 2. **Recall (بازخوانی یا حساسیت):**

### **تعریف:**
Recall نسبت تعداد پیش‌بینی‌های درست به تمام موارد مثبت واقعی است.

### **فرمول:**
\[
\text{Recall} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Negatives (FN)}}
\]

### **هدف:**
از بین تمام نمونه‌های مثبت واقعی، چه تعداد به درستی شناسایی شده‌اند.

### **کاربرد:**
زمانی که هزینه منفی اشتباه (**False Negative**) بالا باشد.

**مثال:**
در تشخیص سرطان (Cancer Detection): 
- اگر یک بیمار سرطانی به اشتباه سالم تشخیص داده شود، ممکن است درمان حیاتی از دست برود. در اینجا Recall بالا بسیار مهم است.

### **مثال کد در پایتون:**
```python
from sklearn.metrics import recall_score

# مقادیر واقعی و پیش‌بینی‌شده
y_true = [0, 1, 1, 0, 1]  # مقادیر واقعی
y_pred = [0, 1, 0, 0, 1]  # مقادیر پیش‌بینی‌شده

# محاسبه Recall
recall = recall_score(y_true, y_pred)
print("Recall:", recall)
```

---

## 3. **تفاوت Precision و Recall:**

| **ویژگی**          | **Precision**                                       | **Recall**                                         |
|---------------------|-----------------------------------------------------|---------------------------------------------------|
| **تمرکز**          | دقت پیش‌بینی‌های مثبت مدل                          | پوشش نمونه‌های مثبت واقعی                          |
| **بهینه‌سازی برای**| کاهش پیش‌بینی مثبت اشتباه (FP)                     | کاهش پیش‌بینی منفی اشتباه (FN)                   |
| **زمان کاربرد**     | زمانی که هزینه مثبت اشتباه بالا باشد                | زمانی که هزینه منفی اشتباه بالا باشد              |

---

## 4. **F1-Score:**

### **تعریف:**
F1-Score میانگینی هماهنگ از Precision و Recall است که برای ایجاد تعادل بین این دو معیار استفاده می‌شود.

### **فرمول:**
\[
\text{F1-Score} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}
\]

### **مثال کد در پایتون:**
```python
from sklearn.metrics import f1_score

# مقادیر واقعی و پیش‌بینی‌شده
y_true = [0, 1, 1, 0, 1]  # مقادیر واقعی
y_pred = [0, 1, 0, 0, 1]  # مقادیر پیش‌بینی‌شده

# محاسبه F1-Score
f1 = f1_score(y_true, y_pred)
print("F1-Score:", f1)
```

---

## 5. **جمع‌بندی:**
- **Precision:** تمرکز بر دقت پیش‌بینی‌های مثبت.
- **Recall:** تمرکز بر شناسایی تمام موارد مثبت واقعی.
- **F1-Score:** توازن بین Precision و Recall.

انتخاب معیار مناسب به مسئله و هزینه خطاهای مثبت یا منفی بستگی دارد.
