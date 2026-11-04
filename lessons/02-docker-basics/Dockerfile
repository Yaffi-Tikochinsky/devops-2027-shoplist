# image בסיס: Python 3.11 בגרסה קטנה (slim), עם גרסה מדויקת ולא latest
FROM python:3.11-slim

# תיקיית העבודה בתוך ה-container. נוצרת אוטומטית אם לא קיימת
WORKDIR /app

# קודם מעתיקים רק את רשימת התלויות, כדי שה-cache יעבוד
COPY requirements.txt .

# מתקינים את התלויות (flask). הדגלים נדרשים ברשת של נטפרי
RUN pip install --no-cache-dir --trusted-host pypi.org --trusted-host files.pythonhosted.org -r requirements.txt

# רק עכשיו מעתיקים את הקוד עצמו
COPY app.py .

# תיעוד: האפליקציה מאזינה על פורט 8000 (לא פותח את הפורט בפועל)
EXPOSE 8000

# הפקודה שרצה כשה-container עולה, בצורת exec (סוגריים מרובעים)
CMD ["python", "app.py"]
