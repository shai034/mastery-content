# mastery-content

תוכן ההקניה של אפליקציית מאסטרי (מסע החשבון), כיתה ה׳.
התוכן כתוב לתלמידים שלומדים לבד, ונבדק במתמטיקה ובעברית. אין כאן קוד, רק תוכן.

## מה יש בריפו

- `grade5/<topic_key>.json`: קובץ אחד לכל נושא (17 קבצים).
- `grade5/all-topics.json`: כל 17 הנושאים במערך אחד, לפי סדר הטבלה.
- `grade5/מאסטרי_כיתה_ה_יחידות_הקניה.pdf`: כל היחידות בקובץ קריא אחד, לבדיקה ולהדפסה.

## הנושאים

| מס׳ | נושא | topic_key | קובץ |
|---|---|---|---|
| 1 | מספרים גדולים | `big-numbers` | `grade5/big-numbers.json` |
| 2 | ארבע פעולות החשבון | `operations` | `grade5/operations.json` |
| 3 | עיגול ואומדן | `rounding` | `grade5/rounding.json` |
| 4 | מספרים ראשוניים ופריקים | `primes` | `grade5/primes.json` |
| 5 | פירוק לגורמים | `factorization` | `grade5/factorization.json` |
| 6 | מה זה שבר? | `fraction-meaning` | `grade5/fraction-meaning.json` |
| 7 | צמצום והרחבה | `simplify-expand` | `grade5/simplify-expand.json` |
| 8 | השוואת שברים | `compare-fractions` | `grade5/compare-fractions.json` |
| 9 | חיבור וחיסור שברים א׳ | `add-sub-fractions-1` | `grade5/add-sub-fractions-1.json` |
| 10 | חיבור וחיסור שברים ב׳ | `add-sub-fractions-2` | `grade5/add-sub-fractions-2.json` |
| 11 | מהו שבר עשרוני? | `decimals-intro` | `grade5/decimals-intro.json` |
| 12 | פי 10, פי 100 ופי 1,000 | `decimals-times10` | `grade5/decimals-times10.json` |
| 13 | חיבור וחיסור עשרוניים | `decimals-add-sub` | `grade5/decimals-add-sub.json` |
| 14 | גובה ושטח משולש | `triangle-area` | `grade5/triangle-area.json` |
| 15 | גובה ושטח מקבילית | `parallelogram-area` | `grade5/parallelogram-area.json` |
| 16 | מנסרות ופירמידות | `solids` | `grade5/solids.json` |
| 17 | חקר נתונים | `data` | `grade5/data.json` |

## מבנה ה־JSON, שדה אחרי שדה

כל קובץ נושא הוא אובייקט אחד עם השדות האלה, בסדר הזה:

| שדה | סוג | מה יש בו |
|---|---|---|
| `grade` | מחרוזת | תמיד `"כיתה ה׳"`. |
| `topic_key` | מחרוזת | המזהה של הנושא במערכת, למשל `big-numbers`. זהה לשם הקובץ. |
| `topic_title` | מחרוזת | שם הנושא לתצוגה. |
| `goal` | מחרוזת | מטרת הלמידה, משפט אחד שפונה לתלמיד. |
| `steps` | מערך של 5 אובייקטים | חמשת שלבי ההקניה, לפי הסדר. |
| `steps[].title` | מחרוזת | כותרת קצרה של השלב. |
| `steps[].text` | מחרוזת | ההסבר לתלמיד. פסקאות מופרדות ב־`\n`, וכל פסקה מוצגת כפסקה נפרדת. |
| `steps[].visual_description` | מחרוזת | הוראות לבניית ההמחשה של השלב: מה לצייר, כמויות, צבעים וכיתובים. זו הוראה לבונה, לא טקסט לתלמיד. |
| `worked_example` | אובייקט | דוגמה פתורה. |
| `worked_example.question` | מחרוזת | השאלה. |
| `worked_example.steps` | מערך של 2 עד 4 מחרוזות | צעדי הפתרון, כל צעד אומר מה עושים ולמה. |
| `worked_example.answer` | מחרוזת | התשובה הסופית. |
| `understanding_check` | אובייקט | שאלת בדיקת הבנה. |
| `understanding_check.question` | מחרוזת | השאלה. |
| `understanding_check.choices` | מערך של 3 מחרוזות | שלוש אפשרויות. שתי השגויות הן טעויות אופייניות. |
| `understanding_check.correct_index` | מספר | מיקום התשובה הנכונה במערך `choices`, **מתחיל מ־0**: 0 היא הראשונה, 1 השנייה, 2 השלישית. |
| `understanding_check.hint` | מחרוזת | רמז שמוצג לפני הבחירה ולא מגלה את התשובה. |
| `understanding_check.explanation` | מחרוזת | הסבר שמוצג אחרי הבחירה: למה הנכונה נכונה ולמה כל אחת מהאחרות שגויה. |
| `common_mistake` | מחרוזת | טעות נפוצה ואיך להימנע ממנה. |
| `teacher_notes` | מחרוזת | הערות קצרות למורה. לא מיועד לתלמיד. |

## הערות לבונים

- **ההמחשות**: אין בריפו תמונות. כל המחשה נבנית במאסטרי לפי `visual_description` של השלב, כולל הכמויות והכיתובים שכתובים שם.
- **הסרטון**: בכל נושא, סרטון ההסבר הקיים משתלב אחרי השלב הראשון (`steps[0]`). אין בתוכן קישורים לסרטונים.
- **כיוון כתיבה**: הטקסט בעברית (RTL), אבל ביטויים מתמטיים כמו `50 - 2 × (8 + 7) = 20` ומספרים מעורבים כמו `2 1/3` נכתבים משמאל לימין. בתצוגה כדאי לעטוף כל ביטוי כזה ב־`<bdi dir="ltr">` (או `unicode-bidi: isolate; direction: ltr`), אחרת הדפדפן עלול להפוך את סדר המספרים.
- **סימנים**: כפל `×`, חילוק `:`, שבר בכתיבה בשורה `3/4`, פסיק מפריד אלפים `4,250,316`, נקודה עשרונית `0.25`.
- הקבצים בקידוד UTF-8.
