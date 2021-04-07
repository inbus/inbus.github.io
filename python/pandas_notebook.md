# Pandas 筆記

## 將讀入的資料欄位A 轉換成日期型態
df = pd.read_csv('z',sep='|',header=None,names=['a','b'],parse_dates=['a'])

## 與下一筆資料做計算
df.a - df.a.shift(1)

## 日期計算後以分鐘產出
(df.a - df.a.shift(1)).astype('timedelta64[m]')
