import pandas as pd

# لیست لیگ های فوتبال
ligues = {
    "1": "پریمیر لیگ انگلیس",
    "2": "لالیگای اسپانیا",
    "3": "بوندسلیگای آلمان"
}

# سال های گذشته
past_years = [2022, 2023]

# دریافت انتخاب کاربر
while True:
    print("\nلیگ مورد نظر خود را انتخاب کنید:")
    for key, value in leagues.items():
        print(f"{key}. {value}")

    انتخاب_لیگ = input("انتخاب شما (1-3): ")

    if انتخاب_لیگ in leagues:
        break
    else:
        print("انتخاب نامعتبر است. لطفاً عددی بین 1 تا 3 را وارد کنید.")

# نمایش عناوین سه سال گذشته
print("\nسال های موجود:")
for year in past_years:
    df = pd.read_csv(f"{ligues[انتخاب_لیگ]}_{year}.csv")
    print(f"{year} - {df.head(1)['Season'].values[0]}")

# دریافت انتخاب سال
while True:
    انتخاب_سال = input("\nسال مورد نظر خود را از بین سال های بالا انتخاب کنید (سال): ")

    if انتخاب_سال.isdigit() and int(انتخاب_سال) in past_years:
        break
    else:
        print("انتخاب نامعتبر است. لطفاً سالی از بین سال های نمایش داده شده را وارد کنید.")

# بارگذاری داده ها
df = pd.read_csv(f"{ligues[انتخاب_لیگ]}_{انتخاب_سال}.csv")

# مرتب سازی جدول بر اساس امتیاز
df = df.sort_values(by=['Pts'], ascending=False)

# نمایش عناوین ستون ها
print(df.columns)

# نمایش 10 ردیف اول جدول
print(df.head(10))
